# 🚀 NestJS CLI Shortcut Commands

## 📦 Common Commands

| Purpose                   | Command                             | Description                              |
|--------------------------|-------------------------------------|------------------------------------------|
| Create new project        | ```bash nest new project-name```             | Scaffolds a new NestJS project           |
| Generate module           | ```bash nest g mo module-name```             | Creates a new module                     |
| Generate controller       | ```bash nest g co controller-name```         | Creates a new controller                 |
| Generate service          | ```bash nest g s service-name```             | Creates a new service                    |
| Generate provider         | ```bash nest g provider provider-name```     | Creates a new provider                   |
| Generate middleware       | ```bash nest g middleware middleware-name``` | Creates a middleware                     |
| Generate interceptor      | ```bash nest g interceptor interceptor-name```| Creates an interceptor                   |
| Generate guard            | ```bash nest g guard guard-name```           | Creates a guard                          |
| Generate pipe             | ```bash nest g pipe pipe-name```             | Creates a pipe                           |
| Generate gateway          | ```bash nest g gateway gateway-name```       | Creates a WebSocket gateway              |
| Generate resolver         | ```bash nest g resolver resolver-name```     | Creates a GraphQL resolver               |
| Run the app               | ```npm run start``` or ```bash nest start```     | Starts the development server            |
| Start in watch mode       | ```npm run start:dev``` or ```bash nest start --watch``` | Auto-restarts on file changes  |
| Run tests                | ```bash npm run test```                      | Runs all unit tests                      |
| Run e2e tests            | ```bash npm run test:e2e```                  | Runs end-to-end tests                    |
| Build the project         | ```bash npm run build```                     | Compiles the TypeScript code             |

---

## ✅ Abbreviations in CLI

- `g` = `generate`
- `mo` = `module`
- `co` = `controller`
- `s` = `service`

---

## 🧠 Example Usage

```bash
nest g mo auth           # Generates auth.module.ts
nest g co auth --flat    # Generates auth.controller.ts without a folder
nest g s auth            # Generates auth.service.ts
