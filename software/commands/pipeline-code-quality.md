# /pipeline-code-quality: Code Quality Pipeline

Run the full code quality pipeline on recent changes or a specific file.

## Steps

### 1. Code review
Review code for bugs, performance issues, security vulnerabilities, and adherence to project standards.

Output: review findings.

### 2. Test
Write comprehensive tests covering the reviewed code. Focus on edge cases, failure modes, and regression prevention.

Output: test files.

### 3. Debug
Fix any bugs or issues identified during review or testing. Trace root causes before applying fixes.

Output: bug fixes with explanations.

### 4. Refactor
Safely restructure code for clarity and maintainability while preserving behavior. Verify all tests still pass.

Output: refactored code.

## How to use

Run: `/pipeline-code-quality [file or description of changes]`
