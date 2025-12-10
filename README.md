# VitestSetup
Vitest Configuration in React + MUI + Vite Project

Step 1 : npm i -D vitest jsdom @testing-library/react @testing-library/user-event @testing-library/jest-dom <br>
Step 2:  Create setup.ts file in tests folder in src <br>
import { afterEach, vi } from 'vitest'; <br>
import { cleanup } from '@testing-library/react'; <br>
import '@testing-library/jest-dom'; <br>

afterEach(()=>{<br>
    cleanup();<br>
    vi.clearAllMocks()<br>
})<br>
Step 3: Create another file called vitest.config.ts in the project folder <br>
import { defineConfig } from 'vitest/config'<br>

export default defineConfig({<br>
  test: {<br>
    globals: true,<br>
    environment: 'jsdom',<br>
    setupFiles: './src/tests/setup'<br>
  }<br>
})<br>
Step 4: Add this in package.json :<br>
 "test": "vitest"<br>

Step 5: Add this in ts.config.json:<br>
  ],<br>
  "compilerOptions": {<br>
    "types": [<br>
      "vitest/globals",<br>
      "@testing-library/jest-dom"<br>
    ]<br>
  }<br>
Steo 6: Add this in tsconfig.app.json:
"types": [
      "vitest/globals",
      "@testing-library/jest-dom"
    ]


