# Permissions

## Levels
### SAFE
Read-only, bounded, low-risk actions may execute automatically.

### CAUTION
Actions that change project state or execute predefined local workflows require stronger policy evaluation and may require approval.

### RESTRICTED
Potentially destructive, privileged, credential-related, external, or generic execution requires explicit user approval.

## Default Policy
Unknown tool: DENY.
Unknown path: DENY.
Unknown permission: DENY.
Invalid arguments: DENY.
Policy unavailable: DENY.

## Examples
- `read_file`: SAFE
- `write_file`: CAUTION
- `delete_file`: RESTRICTED
- `git_status`: SAFE
- `git_commit`: CAUTION
- `git_push`: RESTRICTED
- arbitrary shell: RESTRICTED

Approval is specific to the requested action and should not silently grant broad future permission.
