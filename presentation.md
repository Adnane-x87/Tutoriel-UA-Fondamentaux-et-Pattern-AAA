---
marp: true
theme: default
paginate: true
backgroundColor: "#09090b"
color: "#fafafa"
style: |
  section {
    font-family: 'JetBrains Mono', monospace;
    font-size: 24px;
    border: 1px solid #27272a;
    padding: 60px 80px;
  }
  h1 { color: #f4f4f5; font-size: 2.2em; margin-top: 150px; }
  h2 { color: #3b82f6; font-size: 1.8em; border-bottom: 1px solid #27272a; padding-bottom: 10px; }
  h3 { color: #a1a1aa; }
  code { background: #18181b; color: #60a5fa; border: 1px solid #27272a; border-radius: 6px; padding: 2px 6px; }
  pre { background: #18181b; border: 1px solid #27272a; border-left: 4px solid #3b82f6; border-radius: 10px; padding: 20px; }
  blockquote { background: #18181b; border-left: 4px solid #3b82f6; color: #d1d5db; padding: 10px 20px; }
  
  .logo-header {
    display: flex;
    justify-content: flex-start;
    align-items: center;
    gap: 30px;
    position: absolute;
    top: 30px;   
    left: 60px;
    right: 60px;
  }
  
  .logo-header img {
    height: 70px;  
    width: auto;   
    object-fit: contain;
  }
  
  .dt-card {
    background: #18181b;
    padding: 25px;
    border-radius: 10px;
    border: 1px solid #27272a;
    border-top: 4px solid #3b82f6;
    margin-top: 20px;
  }
  
  .highlight { color: #3b82f6; font-weight: bold; }
  .success { color: #4ade80; }
  .danger { color: #f87171; }
---

<div class="logo-header">
  <img src="./images/ofppt-logo.png" alt="OFPPT">
  <img src="./images/logo-solicode.png" alt="Solicode">
</div>

# **Pattern AAA (Arrange-Act-Assert)**
### Standard de l'écriture des Tests

**Réalisé par :** <span class="highlight">Adnane Kesksu</span>  
**Encadré par :** <span class="highlight">M. ESSARRAJ Fouad</span>  

---

### 1. Introduction

- **Testing** is a method for verifying that code functions correctly.
- In **Laravel**, tests allow you to quickly detect errors and ensure the quality of your project.

---

### 2. What is a Test?

- A test is a small program that checks a specific behavior.

**Simple example:**
> Check that `2 + 3 = 5`

---

### 3. The AAA Pattern

- The AAA pattern is a method for organizing tests.

It contains three steps:

1. **Arrange (Preparation)**
   The data needed for the test is prepared.

2. **Act (Action)**
   The code to be tested is executed.

3. **Assert (Verification)**
   The result is verified to be correct.

--- 

### 4. Simple Example (PHP)

```php
public function test_addition()
{ 
    // Arrange 
    $a = 2; 
    $b = 3; 

    // Act 
    $result = $a + $b; 

    // Assert 
    $this->assertEquals(5, $result);
}

```
---

### 5. Laravel Example (Real)

```php
public function test_homepage_returns_200()
{
    // Arrange
    // nothing to prepare

    // Act
    $response = $this->get('/');

    // Assert
    $response->assertStatus(200);
}
```

--- 

### 6. Why use AAA?

- Clear test organization
- Easy-to-read code
- Fast error detection
- Standard used in all teams

--- 

### 7. Best Practices
Test Name

The name should explain the behavior:

✔ test_user_can_login
✔ test_homepage_returns_200

✘ test1
✘ check

Mandatory Structure

Always write:

// Arrange
// Act
// Assert

---

### 8. Conclusion

- The AAA pattern is the foundation of testing.

Without AAA → disorganized code
With AAA → clear and professional tests

This is the starting point for understanding all Laravel tests.