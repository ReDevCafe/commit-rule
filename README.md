### Variables and Method Naming:

1. Keep names concise and readable — Avoid variable and method names exceeding 40 characters to maintain clarity.
2. Use descriptive names — Names should convey meaning without requiring additional comments.
3. Casing for accessibility:
    - Public members: use `PascalCase` → Example: `FooName`
    - Private & Protected members: Use `camelCase` → Example: `fooName`
    - Constants: Use `UPPER_CASE_WITH_UNDERSCORES` → Example: `MAX_BUFFER_SIZE`

### Conditions:

1. Avoid deeply nested `if` statements
    
    - Instead of:
        
        ```c
        if(a == b)
        {
        	c();
        }
        ```
        
    - Use:
        
        ```c
        if(a != b) return;
        c();
        ```
        
2. Use early exits to improve readability
    
    - Bad:
        
        ```c
        if(a > 0)
        {
        	if(b > 0)
        	{	
        		c();
        	}
        }
        ```
        
    - Good:
        
        ```c
        if(a > 0) return;
        if(b > 0) return;
        c();
        ```
        
3. Use ternary operators where appropriate, but avoid complexity
    
    - Example:
        
        ```c
        int result = (a > b) ? a : b;
        ```
        

### Loops:

1. Prefer pre-increment (`++i`) over post-increment (`i++`) in loops where possible for better performance:
    
    - Instead of:
        
        ```c
        for (int i = 0; i < n; i++)
        ```
        
    - Use:
        
        ```c
        for (int i = 0; i < n; ++i)
        ```
        
2. Use `break` and `continue` wisely
    
    - Avoid unnecessary loop iterations with `continue`:
        
        ```c
        for (int i = 0; i < n; ++i)
        {
        	char* obj = arr[i];
        	
        	if(!obj) continue;
        	process(obj); 
        }
        ```
        

### Functions & Methods:

1. Keep functions short and focused
    
    - Each function should ideally perform one task only
    - If a function exceeds 100-120 lines, consider refactoring
2. Use meaningful parameter names:
    
    - Bad:
    
    ```c
    void process(int a, int b) { ... }
    ```
    
    - Good:
    
    ```c
    void process(int width, int height) { ... }
    ```
