# 🚀 NestJS CLI Shortcut Commands

### Create a new project
```bash 
nest new project-name
```
### Generate a module
```bash 
nest g mo module-name
```

### Generate a controller
```bash 
nest g co controller-name
```

### Generate a service
```bash 
nest g s service-name
```

### Generate a provider
```bash 
nest g provider provider-name
```

### Generate middleware
```bash 
nest g middleware middleware-name
```

### Generate interceptor
```bash 
nest g interceptor interceptor-name
```

### Generate a guard
```bash 
nest g guard guard-name
```

### Generate a pipe
```bash 
nest g pipe pipe-name
```

### Generate a gateway (WebSocket)
```bash 
nest g gateway gateway-name
```

### Generate a resolver (GraphQL)
```bash 
n##est g resolver resolver-name
```

### Run the app
```bash 
npm run start
```
### or
nest start
##
### Run in watch mode (auto-reload)
```bash 
npm run start:dev
```
### or
```bash 
nest start --watch
```

### Run unit tests
```bash 
npm run test
```

### Run end-to-end (e2e) tests
```bash 
npm run test:e2e
```

### Build the project
```bash 
npm run build
```

### ✅ CLI Abbreviations
### g  = generate
### mo = module
### co = controller
### s  = service

### 🧠 Example Usage
```bash 
nest g mo auth           # Generates auth.module.ts
nest g co auth --flat    # Generates auth.controller.ts (no folder)
nest g s auth            # Generates auth.service.ts
```
