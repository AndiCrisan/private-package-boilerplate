# 🚀 Private Package Boilerplate

This repository contains a boilerplate setup for creating private TypeScript packages. It includes structured configurations for Zod schema validation and a services folder to interface with third-party services. This setup is ideal for building and maintaining robust and reliable private packages.

## ✨ Features

- **TypeScript**: Ensures type safety and modern JavaScript features.
- **Zod**: Integrated schema validation for data integrity.
- **Services Folder**: Structured approach for interacting with third-party APIs.
- **Standard Directory Structure**: Organized project layout for clarity and maintainability.
- **Build and Test Scripts**: Automate the packaging, testing, and deployment processes.
- **Comprehensive Documentation**: Templates and guidelines for thorough documentation.

## 🛠️ Getting Started

### Prerequisites

- [Node.js](https://nodejs.org/) (version 14.x or higher)
- [Yarn](https://yarnpkg.com/) (version 1.22.x or higher)

### 🚀 Installation

1. **Clone the Repository**:
   ```sh
   git clone https://github.com/yourusername/private-package-boilerplate.git
   cd private-package-boilerplate

2. **Install Dependencies**:
   ```sh
   yarn install

3. **Project Structure**:

```
private-package-boilerplate/
├── src/
│   ├── index.ts
│   ├── services/
│   │   ├── exampleService.ts
│   └── types/
│       ├── exampleType.ts
├── tests/
│   ├── exampleService.test.ts
├── .eslintrc.json
├── .gitignore
├── package.json
├── README.md
└── tsconfig.json
```

## 🔧 Usage

### Example Service

The `exampleService.ts` file in the `services` folder demonstrates how to interact with a third-party API using TypeScript and Zod.

```typescript
// src/services/exampleService.ts
import axios from 'axios';
import { z } from 'zod';

// Define a schema for the expected response using Zod
const ExampleResponseSchema = z.object({
  userId: z.number(),
  id: z.number(),
  title: z.string(),
  completed: z.boolean(),
});

type ExampleResponse = z.infer<typeof ExampleResponseSchema>;

export async function fetchExampleData(): Promise<ExampleResponse> {
  const response = await axios.get('https://jsonplaceholder.typicode.com/todos/1');
  return ExampleResponseSchema.parse(response.data);
}
```
