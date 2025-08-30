# General C Coding Style Guide

This guide summarizes a consistent coding style for embedded C projects, inspired by `bsp_flash.c`.

---

## 1. File Structure

- **Header Block:**  
  Each file begins with a multi-line comment containing:
  - File name
  - Copyright
  - License
  - Version
  - Date
  - Author
  - Brief description
  - Notes

- **Section Comments:**  
  Use comments to divide code into logical sections:
  - Includes
  - Private/Public defines, enumerations, macros, variables, function prototypes
  - Function definitions

---

## 2. Naming Conventions

- **Macros & Constants:**  
  Uppercase with underscores (e.g., `MAX_BUFFER_SIZE`, `KEY1`).

- **Functions:**  
  Use a module prefix (e.g., `bsp_flash_*`, `uart_init`).

- **Variables:**  
  Descriptive, lowercase with underscores (e.g., `start_address`, `buffer_write`).

- **Types:**  
  Custom types use `_t` suffix (e.g., `status_t`, `wifi_info_t`).

---

## 3. Formatting

- **Indentation:**  
  Consistent 2-space or 4-space indentation.

- **Braces:**  
  Opening brace on the same line as the statement.

- **Spacing:**  
  Space after commas and operators; avoid unnecessary whitespace.

- **Parentheses:**  
  Use for clarity in conditions and casts.

---

## 4. Comments

- **Section Comments:**  
  Clearly mark code sections.

- **Inline Comments:**  
  Explain complex logic, hardware operations, or non-obvious code.

- **Function Comments:**  
  Briefly describe function purpose and parameters.

---

## 5. Function Implementation

- **Parameter Checking:**  
  Validate input parameters at the start of functions.

- **Return Values:**  
  Use custom status enums or error codes.

- **Timeout Handling:**  
  Use timeout variables for hardware operations to avoid infinite loops.

- **Register Access:**  
  Manipulate hardware registers directly, with explanatory comments.

---

## 6. Type Safety & Casting

- **Explicit Casting:**  
  Use explicit casts for pointer arithmetic and type conversions.

- **Struct and Array Handling:**  
  Use casts when writing/reading structs and arrays to hardware or memory.

---

## 7. Magic Numbers

- **Avoid Magic Numbers:**  
  Define constants for addresses, keys, sizes, etc.

---

## 8. Error Handling

- **Early Return:**  
  Return error status immediately on invalid input or timeout.

---

## 9. Miscellaneous

- **No Dynamic Memory:**  
  Prefer static or stack-allocated buffers.

- **Minimal External Dependencies:**  
  Rely only on necessary headers and hardware registers.

---

## Example Function Skeleton

```c
status_t module_function(uint32_t param1, uint32_t *param2, uint32_t length)
{
  // Check input parameters
  if ((param2 == NULL) || (length == 0))
    return STATUS_ERROR;

  // Hardware operation with timeout
  uint32_t timeout = MODULE_TIMEOUT;
  while ((HW_REG & HW_BUSY) && timeout)
  {
    if (--timeout == 0)
      return STATUS_ERROR;
  }

  // Main logic
  // ...

  return STATUS_OK;
}
```

---

**Use this style for consistency, readability, and maintainability across all C