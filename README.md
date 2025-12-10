# VitestSetup
Vitest Configuration in React + MUI + Vite Project

Step 1 : npm i -D vitest jsdom @testing-library/react @testing-library/user-event @testing-library/jest-dom
Step 2:  Create setup.ts file in tests folder in src
import { afterEach, vi } from 'vitest';
import { cleanup } from '@testing-library/react';
import '@testing-library/jest-dom';

afterEach(()=>{
    cleanup();
    vi.clearAllMocks()
})
Step 3: Create another file called vitest.config.ts in the project folder 
import { defineConfig } from 'vitest/config'

export default defineConfig({
  test: {
    globals: true,
    environment: 'jsdom',
    setupFiles: './src/tests/setup'
  }
})
Step 4: Add this in package.json :
 "test": "vitest"

Step 5: Add this in ts.config.json:
  ],
  "compilerOptions": {
    "types": [
      "vitest/globals",
      "@testing-library/jest-dom"
    ]
  }
Steo 6: Add this in tsconfig.app.json:
"types": [
      "vitest/globals",
      "@testing-library/jest-dom"
    ]


