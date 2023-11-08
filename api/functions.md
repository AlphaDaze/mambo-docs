---
layout: default
title: Functions
parent: API
nav_order: 2
---

## Load and store helper functions

| Function  | Description  |
|:---|:---|
|  `mambo_is_load()`  |  Load instruction |
|  `mambo_is_store()` |  Store instruction |
|  `mambo_get_ld_st_size()` |  Determine data size for load/store |
|  `mambo_calc_ld_st_addr()` |  Determine address of load/store at runtime |



## Branch helper functions

| Function  | Description  |
|:---|:---|
|  `mambo_get_branch_type()`  |  Returns bitwise field: BRANCH_NONE, BRANCH_DREICT, BRANCH_INDIRECT, BRANCH_CONDITIONAL, BRANCH_CALL, BRANCH_RETURN... |
|  `mambo_get_branch_target()` |  Return address of direct branches |
|  `mambo_calc_branch_target()` |  Get indirect branch address at runtime |


## Function Names and Symbols

| Function  | Description  |
|:---|:---|
|  `get_symbol_info_by_addr()`  | Returns symbol data associated with an address such as function and file names |
|  `get_backtrace()` |  Get call backtrace based on a frame pointer |

## Other

| Function  | Description  |
|:---|:---|
|  `mambo_get_inst_regs([...], inset, outset)`  | Input and output registers set by each instruction |
|  `mambo_register_function_cb(context, "fn", &pre, &post)`  | Add pre and post handlers to function fn |