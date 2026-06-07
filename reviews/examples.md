# Code Review Examples

## 1. Magic Numbers / Constants

**Commit message:** `feat: Introduce standard discount rate constant`

**Code:**
```csharp
public class OrderProcessor
{
    public double CalculateFinalPrice(double price, int quantity)
    {
        // ... some logic
        return (price * quantity) * (1 - 0.1); // Magic number 0.1
    }
}
```

**Review:**
> This `0.1` looks like a magic number representing a discount rate. It's unclear what it signifies without additional context and could be easily misinterpreted or changed incorrectly.
>
> **Suggestion:** Extract this value into a named constant, e.g., `const double StandardDiscountRate = 0.1;`, within the class or as a shared constant if used elsewhere. This improves readability and maintainability.

---

## 2. Naming Conventions

**Commit message:** `refactor: Rename 'd' to 'currentTime' for clarity`

**Code:**
```csharp
public class Logger
{
    public void LogEvent(string message)
    {
        var d = DateTime.Now; // Poorly named variable
        Console.WriteLine($"[{d}] {message}");
    }
}
```

**Review:**
> The variable `d` is not descriptive. While its type `DateTime` gives some clue, it's best to use full, explicit names to enhance readability, especially for future maintainers.
>
> **Suggestion:** Rename `d` to `currentTime` or `now`. This makes the code's intent immediately clear.

---

## 3. Missing Error Handling

**Commit message:** `feat: Add file content reader utility`

**Code:**
```csharp
public class FileReader
{
    public string ReadFileContent(string path)
    {
        return File.ReadAllText(path); // No error handling
    }
}
```

**Review:**
> The `ReadFileContent` method directly calls `File.ReadAllText(path)` without any error handling. This can lead to unhandled exceptions (e.g., `FileNotFoundException`, `UnauthorizedAccessException`) if the file doesn't exist, is inaccessible, or the path is invalid.
>
> **Suggestion:**
> 1.  Wrap the file reading operation in a `try-catch` block to gracefully handle potential exceptions and provide meaningful error messages or return a specific error state.
> 2.  Alternatively, if exceptions are intended to propagate, explicitly document the exceptions that can be thrown using XML documentation comments (`<exception>`).

---

## 4. Security Vulnerability (SQL Injection)

**Commit message:** `feat: Implement user search functionality`

**Code:**
```csharp
public class UserRepository
{
    private readonly SqlConnection _connection;

    public UserRepository(SqlConnection connection)
    {
        _connection = connection;
    }

    public List<User> SearchUsers(string searchTerm)
    {
        // SQL Injection vulnerability!
        string query = $"SELECT * FROM Users WHERE UserName LIKE '%{searchTerm}%'";
        using (SqlCommand command = new SqlCommand(query, _connection))
        {
            _connection.Open();
            // ... execute and read data
            _connection.Close();
            return new List<User>(); // Placeholder
        }
    }
}

public class User { /* ... */ }
```

**Review:**
> This code is vulnerable to SQL injection. Directly concatenating `searchTerm` into the SQL query allows malicious input to alter the query's intent, potentially leading to data breaches or unauthorized access.
>
> **Suggestion:** Always use parameterized queries or an Object-Relational Mapper (ORM) when incorporating user input into SQL statements. Replace string concatenation with `SqlParameter` objects:
>
> ```csharp
> string query = "SELECT * FROM Users WHERE UserName LIKE @searchTerm";
> using (SqlCommand command = new SqlCommand(query, _connection))
> {
>     command.Parameters.AddWithValue("@searchTerm", $"%{searchTerm}%");
>     // ...
> }
> ```

---

## 5. Performance / Idioms

**Commit message:** `refactor: Optimize user list filtering`

**Code:**
```csharp
public class UserFilter
{
    public List<User> FilterActiveUsers(List<User> allUsers)
    {
        List<User> activeUsers = new List<User>();
        for (int i = 0; i < allUsers.Count; i++) // Index-based loop for filtering
        {
            if (allUsers[i].IsActive)
            {
                activeUsers.Add(allUsers[i]);
            }
        }
        return activeUsers;
    }
}
```

**Review:**
> The `FilterActiveUsers` method uses an imperative, index-based `for` loop to filter users. While functional, C# offers more idiomatic and often more concise ways to achieve this using Language Integrated Query (LINQ).
>
> **Suggestion:** Utilize LINQ's `.Where()` extension method, which improves readability and expresses intent more clearly:
>
> ```csharp
> public List<User> FilterActiveUsers(List<User> allUsers)
> {
>     return allUsers.Where(user => user.IsActive).ToList();
> }
> ```
> This reduces boilerplate and leverages functional programming patterns available in C#.
