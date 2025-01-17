Pattern: Class used as namespace container

Issue: -

## Description

Using a class solely as a static namespace container adds unnecessary complexity and makes code harder to maintain. Static members can be exported directly from modules, and utility functions don't need class wrapping. Empty classes or those with only constructors can typically be replaced with standalone functions.

## Examples

Example of **incorrect** code:
```ts
// Class as static namespace
class Utils {
  static formatDate(date: Date) {
    return date.toISOString();
  }
  
  static readonly VERSION = '1.0.0';
}

// Empty class
class EmptyClass {}

// Class with only constructor
class Logger {
  constructor() {
    console.log('Initialized');
  }
}

// Static-only class
class Constants {
  static readonly API_URL = 'https://api.example.com';
  static readonly MAX_RETRIES = 3;
}
```

Example of **correct** code:
```ts
// Direct exports
export function formatDate(date: Date) {
  return date.toISOString();
}

export const VERSION = '1.0.0';

// Function instead of constructor-only class
function initLogger() {
  console.log('Initialized');
}

// Constants as exports
export const API_URL = 'https://api.example.com';
export const MAX_RETRIES = 3;

// Class with instance members
class User {
  constructor(private name: string) {}
  
  getName() {
    return this.name;
  }
}

// Abstract class with members
abstract class Base {
  abstract process(): void;
  protected data: string;
}
```