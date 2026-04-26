# 🏆🏆🏆 Trophy Case 🏆🏆🏆

🐛 Bugs and enhancements found with fuzzing and testing.

---

## [Robot Framework](https://robotframework.org)

| Issue | Category |
|-------|----------|
| [String: bad error reporting when bytes conversion fails](https://github.com/robotframework/robotframework/issues/5636) | error-handling |
| [String: invalid `exclude` regex leaks `re.error`](https://github.com/robotframework/robotframework/issues/5648) | error-handling |
| [`get_index_from_list` returns -1 with negative `start` when value is present](https://github.com/robotframework/robotframework/issues/5649) | logic |
| [`TypeInfoParser`: `\|` inside type params causes crash or infinite loop](https://github.com/robotframework/robotframework/issues/5650) | crash / hang |

---

## [Playwright](https://playwright.dev)

| Issue | Category |
|-------|----------|
| [`page.route()` silently aborts navigation when glob contains unbalanced `{` or `}`](https://github.com/microsoft/playwright/issues/40422) | logic |
| [Locator parser: `unsafeLocatorOrSelectorAsSelector` throws on malformed input; `locatorOrSelectorAsSelector` emits unparseable selectors](https://github.com/microsoft/playwright/issues/40427) | error-handling |

---

## [GitHub Copilot SDK](https://github.com/github/copilot-sdk)

| Issue | Category |
|-------|----------|
| [`cliUrl` / `cli_url` parser rejects IPv6 addresses (including bracketed `[::1]:port` form)](https://github.com/github/copilot-sdk/issues/1137) | enhancement |
| [Python codegen: `_compat_to_python_key` / `_compat_to_json_key` are not inverses for keys with common abbreviations (URL, ID, IP, XML, OAuth)](https://github.com/github/copilot-sdk/issues/1138) | logic |
| [`SessionTaskCompleteData` round-trip turns `None` summary into empty string](https://github.com/github/copilot-sdk/issues/1139) | logic |
| [`PermissionPromptRequest.action` round-trip turns `None` into `PermissionPromptRequestMemoryAction.STORE`](https://github.com/github/copilot-sdk/issues/1140) | logic |
| [`PermissionRequest.action` round-trip turns `None` into `PermissionRequestMemoryAction.STORE`](https://github.com/github/copilot-sdk/issues/1141) | logic |
