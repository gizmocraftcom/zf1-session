# Changelog

## 3.0.0

Fork of `diablomedia/zendframework1-session`, published as `gizmocraft/zendframework1-session`.

### Breaking changes

- Requires PHP `>=8.5`. Tested on PHP 8.5 and 8.6.
- Package renamed from `diablomedia/zendframework1-session` to `gizmocraft/zendframework1-session`. It now requires `gizmocraft/zendframework1-exception` `^2.0.0`, `gizmocraft/zendframework1-config` `^3.0.0` and `gizmocraft/zendframework1-loader` `^2.0.0`.

### Other changes

- Dev dependencies upgraded (PHPUnit 13, PHPStan 2.3, php-cs-fixer 3.95, GrumPHP 2.27). Dropped `composer-require-checker`, which has no release for PHP 8.6.
- Tests migrated to PHPUnit 13 attributes. `Zend_Session_SessionTest` no longer overrides the final `TestCase::__construct()`; it builds the helper command in `setUp()` with `PHP_BINARY` (the PHP version under test) and a quoted `include_path`. The dead `catch (PHPUnit\Framework\Error\Notice)` was removed; a notice now fails the test through `failOnNotice`.
- CI runs PHP 8.5 and 8.6.
- No library code changes and no public signature changes. The legacy `session.*` option names accepted by `Zend_Session::setOptions()` (for example `entropy_file`, `bug_compat_42`, `hash_function`) are kept; PHP ignores the ones it no longer has.
