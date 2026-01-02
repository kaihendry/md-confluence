---
title: Code Examples
sync_to_confluence: true
---

# Code Examples

Testing inline code and code blocks for markdown-confluence-sync-action.

## Inline Code

Use `npm install` to install dependencies. The config file is `config.yaml`.

Variables like `myVariable` and functions like `calculateTotal()` should render inline.

Mix text with `code` and **bold** and *italic* formatting.

## Code Blocks by Language

### JavaScript

```javascript
const express = require('express');
const app = express();

app.get('/api/users', async (req, res) => {
  const users = await User.findAll();
  res.json(users);
});

app.listen(3000, () => {
  console.log('Server running on port 3000');
});
```

### TypeScript

```typescript
interface User {
  id: number;
  name: string;
  email: string;
  createdAt: Date;
}

async function fetchUser(id: number): Promise<User> {
  const response = await fetch(`/api/users/${id}`);
  return response.json();
}
```

### Python

```python
from dataclasses import dataclass
from typing import List

@dataclass
class User:
    id: int
    name: str
    email: str

def get_active_users(users: List[User]) -> List[User]:
    return [u for u in users if u.is_active]

if __name__ == "__main__":
    print("Hello, World!")
```

### Bash / Shell

```bash
#!/bin/bash

# Deploy script
echo "Starting deployment..."

git pull origin main
npm ci
npm run build

pm2 restart app

echo "Deployment complete!"
```

### YAML

```yaml
name: CI Pipeline
on:
  push:
    branches: [main]

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - name: Install dependencies
        run: npm ci
      - name: Run tests
        run: npm test
```

### JSON

```json
{
  "name": "my-project",
  "version": "1.0.0",
  "dependencies": {
    "express": "^4.18.0",
    "lodash": "^4.17.21"
  },
  "scripts": {
    "start": "node index.js",
    "test": "jest"
  }
}
```

### SQL

```sql
SELECT 
    u.id,
    u.name,
    COUNT(o.id) as order_count
FROM users u
LEFT JOIN orders o ON u.id = o.user_id
WHERE u.created_at > '2024-01-01'
GROUP BY u.id, u.name
HAVING COUNT(o.id) > 5
ORDER BY order_count DESC;
```

### HTML

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>My Page</title>
</head>
<body>
    <header>
        <h1>Welcome</h1>
    </header>
    <main>
        <p>Hello, World!</p>
    </main>
</body>
</html>
```

### CSS

```css
.container {
  display: flex;
  flex-direction: column;
  gap: 1rem;
  max-width: 1200px;
  margin: 0 auto;
}

.card {
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  border-radius: 8px;
  padding: 1.5rem;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
}
```

### Go

```go
package main

import (
    "fmt"
    "net/http"
)

func handler(w http.ResponseWriter, r *http.Request) {
    fmt.Fprintf(w, "Hello, %s!", r.URL.Path[1:])
}

func main() {
    http.HandleFunc("/", handler)
    http.ListenAndServe(":8080", nil)
}
```

### Rust

```rust
use std::collections::HashMap;

fn main() {
    let mut scores: HashMap<String, i32> = HashMap::new();
    
    scores.insert(String::from("Blue"), 10);
    scores.insert(String::from("Red"), 50);
    
    for (key, value) in &scores {
        println!("{}: {}", key, value);
    }
}
```

## Plain Code Block (no language)

```
This is a plain code block
without syntax highlighting.
Just preformatted text.
```

## Diff / Patch

```diff
- const oldValue = "before";
+ const newValue = "after";

  function unchanged() {
    return true;
  }

- removeThis();
+ addThis();
```

## Expected Results

| Feature | Expected |
|---------|----------|
| Inline code | Monospace font, slight background |
| Code blocks | Syntax highlighting (if `rehype.codeBlocks: true`) |
| Language labels | May show language name |
| Line numbers | Depends on Confluence config |
| Copy button | Native Confluence feature |

## Notes

- Enable `rehype.codeBlocks: true` in the action config for Confluence code macro
- Without it, code renders as preformatted text
- Confluence supports many languages but may map them differently
