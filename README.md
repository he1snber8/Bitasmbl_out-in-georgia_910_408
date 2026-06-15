# Quickstart for Bitasmbl project (.NET)

## 1) Install Bitasmbl-CLI package

```bash
npm i bitasmbl-cli
```

## 2) Run bitasmbl command to set up the project

```bash
bitasmbl pull --repoUrl https://github.com/he1snber8/Bitasmbl_out-in-georgia_910_408 --appId 408 --repoId 232
```

## 3) Enter into the main directory and start coding!

```bash
cd Bitasmbl_out-in-georgia_910_408
```

## Customize requirements in a way you like

Bitasmbl organizes development into requirements. Each requirement describes a feature or implementation goal and can define suggested file locations through a `paths` array.

The `paths` property acts as a mapping guideline, helping contributors understand where related code should live.

You can customize `paths` mappings through the `bitasmbl.json` file.

{"Requirement":"Implement lobby UI","Paths":["ui/**","public/**","views/lobby/**"]}


## What you should do

### Implement lobby UI

Create screens to list rooms, join, create games, and show basic player presence without complex logic.

### Set up real-time transport

Wire a basic real-time connection so player join/leave and simple game events sync across clients.

### Create game session handling

Manage creation, joining, leaving and teardown of game rooms with minimal state tracking.

### Design simple game flow

Implement a basic human-playable turn or round flow with clear states and simple transitions only.

### Add minimal persistence

Store lightweight room and player metadata so sessions survive simple restarts or page reloads.



## Requirement Evaluation

Bitasmbl includes a requirement evaluation workflow that lets contributors select a task and submit work for validation.

Run:

```bash
bitasmbl evaluate
```

Example output:

<pre>
? Available Requirements:

❯ [<span style="color:#9333ea">1</span>] <span style="color:#9333ea"> Define portfolio layout </span>            [3]
  [2] Build showcase components            [3]
  [3] Implement navigation routing         [3]
</pre>

`[x]` on the right represents the number of submission attempts remaining for a requirement.

## Example evaluation result

```csharp
/*
|--------------------------------------------------------------------------
| BITASMBL EVALUATION
|--------------------------------------------------------------------------
| REQUIREMENT:
| Implement product catalog API
|
| SCORE: 12/100
| STATUS: FAIL ✕
|
| INSIGHT:
| The endpoint returns static product data and does not use a repository,
| service layer, filtering, or async database access.
|--------------------------------------------------------------------------
*/

using Microsoft.AspNetCore.Mvc;

namespace BitasmblProject.Features.Catalog;

[ApiController]
[Route("api/products")]
public sealed class ProductsController : ControllerBase
{
    [HttpGet]
    public IActionResult GetProducts()
    {
        var products = new[]
        {
            new { Id = 1, Name = "Keyboard", Price = 89.99 },
            new { Id = 2, Name = "Mouse", Price = 49.99 }
        };

        return Ok(products);
    }
}
```


## Final project evaluation 

final project info ui will display here

## Learn More

For complete command references, workflow explanations, and additional documentation, visit:

👉 [Bitasmbl Documentation](https://bitasmbl.com/docs)