# bug_pants_chumpy

## Reproduce

```bash
pants  generate-lockfiles
```

## Error

```
12:17:50.97 [INFO] Initializing scheduler...
12:17:50.97 [WARN] File handle limit is capped to: 4096. To avoid 'too many open file handle' errors, we recommend a limit of at least 10000: please see https://www.pantsbuild.org/docs/troubleshooting#too-many-open-files-error for more information.
12:17:52.72 [INFO] Scheduler initialized.
12:17:56.31 [INFO] Completed: Generate lockfile for python-default
12:17:56.31 [ERROR] 1 Exception encountered:

Engine traceback:
  in `generate-lockfiles` goal

ProcessExecutionFailure: Process 'Generate lockfile for python-default' failed with exit code 1.
stdout:

stderr:
Traceback (most recent call last):
  File "<string>", line 9, in <module>
ModuleNotFoundError: No module named 'pip'

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File "/home/username/.cache/pants/named_caches/pex_root/venvs/b9adfa99c6d6b79608a42a3f98befc193d4b4a8b/f13f9d017daafbd389fbe4d321af406e6d9755f3/pex", line 263, in <module>
    exec(ast, globals_map, locals_map)
  File "-c <cmd>", line 10, in <module>
  File "/home/username/.cache/pants/named_caches/pex_root/venvs/b9adfa99c6d6b79608a42a3f98befc193d4b4a8b/f13f9d017daafbd389fbe4d321af406e6d9755f3/lib/python3.11/site-packages/setuptools/build_meta.py", line 341, in get_requires_for_build_wheel
    return self._get_build_requires(config_settings, requirements=['wheel'])
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/home/username/.cache/pants/named_caches/pex_root/venvs/b9adfa99c6d6b79608a42a3f98befc193d4b4a8b/f13f9d017daafbd389fbe4d321af406e6d9755f3/lib/python3.11/site-packages/setuptools/build_meta.py", line 323, in _get_build_requires
    self.run_setup()
  File "/home/username/.cache/pants/named_caches/pex_root/venvs/b9adfa99c6d6b79608a42a3f98befc193d4b4a8b/f13f9d017daafbd389fbe4d321af406e6d9755f3/lib/python3.11/site-packages/setuptools/build_meta.py", line 488, in run_setup
    self).run_setup(setup_script=setup_script)
          ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/home/username/.cache/pants/named_caches/pex_root/venvs/b9adfa99c6d6b79608a42a3f98befc193d4b4a8b/f13f9d017daafbd389fbe4d321af406e6d9755f3/lib/python3.11/site-packages/setuptools/build_meta.py", line 338, in run_setup
    exec(code, locals())
  File "<string>", line 11, in <module>
ModuleNotFoundError: No module named 'pip'
Could not gather lock metadata for 1 project with source artifacts:
1. /tmp/pants-sandbox-7kXwM2/.tmp/tmp5tkhm1uz/home.username..pyenv.versions.3.11.3.bin.python3.11/chumpy-0.70.tar.gz: Executing /home/username/.cache/pants/named_caches/pex_root/venvs/b9adfa99c6d6b79608a42a3f98befc193d4b4a8b/f13f9d017daafbd389fbe4d321af406e6d9755f3/bin/python -sE /home/username/.cache/pants/named_caches/pex_root/venvs/b9adfa99c6d6b79608a42a3f98befc193d4b4a8b/f13f9d017daafbd389fbe4d321af406e6d9755f3/pex -c import json
import sys

import setuptools.build_meta


if not hasattr(setuptools.build_meta.__legacy__, 'get_requires_for_build_wheel'):
    sys.exit(75)

result = setuptools.build_meta.__legacy__.get_requires_for_build_wheel(*(), **{})
with open('/tmp/pants-sandbox-7kXwM2/.tmp/tmpeajib68s', "w") as fp:
    json.dump(result, fp)
 failed with 1



Use `--keep-sandboxes=on_failure` to preserve the process chroot for inspection.
```