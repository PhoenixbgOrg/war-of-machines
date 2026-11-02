# Third-party notices / Уведомления за компоненти на трети страни

**War of Machines 0.1.1-beta, compiled standalone build for Linux x86_64 (Nuitka 4.3.4). Prepared, not released.** This page lists what the release package will contain. The `THIRD_PARTY_LICENSES/` folder mentioned below is inside the release package.

**EN.** This package **bundles** the third-party components listed below in compiled or shared-library form. Each component remains under its own licence. The War of Machines Freeware License does not apply to them and **does not restrict any right you have under their licences** (Freeware License, clause 10.2). Full licence texts are in the `THIRD_PARTY_LICENSES/` folder.

**BG.** Този пакет **включва** изброените по-долу компоненти на трети страни в компилиран вид или като споделени библиотеки. Всеки компонент остава под собствения си лиценз. Лицензът на War of Machines не се прилага за тях и **не ограничава правата Ви по техните лицензи** (т. 10.2). Пълните текстове са в папката `THIRD_PARTY_LICENSES/`.

## Qt and Qt for Python (PySide6, shiboken6): LGPL-3.0 notice

**This application uses Qt 6 and Qt for Python (PySide6) under the GNU Lesser General Public License version 3 (LGPL-3.0).** Qt is a trademark of The Qt Company Ltd. Versions: Qt 6.12.0, PySide6-Essentials 6.12.0, shiboken6 6.12.0, all unmodified.
- **Separate, replaceable libraries.** All Qt, PySide6 and shiboken6 code is shipped as separate shared libraries in `app/`. There is no onefile archive.
  - `app/libQt6*.so.6` and `app/libicu*.so.73`
  - `app/libpyside6.abi3.so.6.12` and `app/libshiboken6.abi3.so.6.12`
  - `app/PySide6/QtCore.so`, `QtGui.so` and `QtWidgets.so`
  - `app/shiboken6/Shiboken.so`
  - the `app/PySide6/qt-plugins/` folder
- **Replacing them.** To use a modified or different build of Qt 6.12 / PySide6 6.12, build it with the same ABI (x86_64, glibc ≤ 2.41, Qt 6.12 binary compatibility). Then overwrite the matching files in `~/.local/share/war-of-machines/app/` (or the unpacked `app/` folder) and start the program. The executable loads these libraries from its own directory at run time (RPATH `$ORIGIN`), so the executable itself does not need to be relinked. To check what is actually loaded, use `ldd ~/.local/share/war-of-machines/app/war-of-machines` or `LD_DEBUG=libs`.
- **Source code** for the exact versions:
  - Qt 6.12.0: https://download.qt.io/official_releases/qt/6.12/6.12.0/single/
  - Qt for Python 6.12.0: https://download.qt.io/official_releases/QtForPython/pyside6/ (sdist `pyside6-6.12.0`) and https://code.qt.io/cgit/pyside/pyside-setup.git/tag/?h=v6.12.0
  - Copies of the source for these versions can also be requested from info@ritualforgelabs.com for at least three years after this release.
- **Licence texts:** `THIRD_PARTY_LICENSES/PySide6_Essentials-6.12.0/` and `THIRD_PARTY_LICENSES/shiboken6-6.12.0/` contain the LGPL-3.0, GPL-3.0 and GPL-2.0 texts.
- **Third-party code inside Qt** (ICU, harfbuzz, freetype, libpng, libjpeg, pcre2, md4c, double-conversion, zlib and others) is listed at https://doc.qt.io/qt-6/licenses-used-in-qt.html. The ICU licence is in `THIRD_PARTY_LICENSES/ICU-73-bundled-by-Qt/`.
- **No GPL-only Qt modules** are included. The Qt Virtual Keyboard plugin is removed at build time.
- You may reverse-engineer War of Machines to the extent needed to debug your modifications of these libraries (LGPL-3.0 §4 and Freeware License clause 10.2).

**BG.** Приложението използва Qt 6 и Qt for Python (PySide6) под GNU LGPL версия 3.
- Библиотеките са отделни файлове `.so` в папката `app/` и можете да ги замените със съвместима (включително променена) версия 6.12, като презапишете съответните файлове. Изпълнимият файл ги зарежда от собствената си папка.
- Изходният код е на връзките по-горе.

## Other trademarks / Други търговски марки

`wom/assets/paypal-mark-color.svg` is bundled unmodified, from https://www.paypalobjects.com/. PayPal and the PayPal logo are trademarks of PayPal, Inc. They are used only to identify the voluntary support button; no affiliation or endorsement is implied. Provider names (OpenAI, xAI, Anthropic, Google Gemini, Mistral, DeepSeek, OpenRouter, Ollama) are trademarks of their owners and are used only to identify compatible services.

## Bundled components / Включени компоненти

| Component | Version | Licence | Form in package | Licence text in THIRD_PARTY_LICENSES/ |
|---|---|---|---|---|
| Qt 6 (Core, Gui, Widgets, DBus, Network, OpenGL, PrintSupport, Svg, XcbQpa, WaylandClient, WlShellIntegration, EglFS*, Qml*, Quick, plugins) | 6.12.0 | LGPL-3.0 (chosen option of LGPL-3.0/GPL-2.0/GPL-3.0) | shared libraries | PySide6_Essentials-6.12.0/ |
| PySide6-Essentials | 6.12.0 | LGPL-3.0 | shared libraries | PySide6_Essentials-6.12.0/ |
| shiboken6 | 6.12.0 | LGPL-3.0 | shared libraries | shiboken6-6.12.0/ |
| ICU (part of the Qt wheel) | 73 | Unicode License (ICU) | shared libraries | ICU-73-bundled-by-Qt/ |
| Python runtime | 3.13.5 | PSF-2.0 | compiled into the executable | Python-3.13.5/ |
| Nuitka runtime | 4.3.4 | AGPL-3.0 with the Nuitka Runtime Library Exception | compiled into the executable | Nuitka-runtime-4.3.4/ |
| httpx | 0.28.1 | BSD-3-Clause | compiled | httpx-0.28.1/ |
| httpcore | 1.0.9 | BSD-3-Clause | compiled | httpcore-1.0.9/ |
| h11 | 0.16.0 | MIT | compiled | h11-0.16.0/ |
| anyio | 4.16.0 | MIT | compiled | anyio-4.16.0/ |
| idna | 3.20 | BSD-3-Clause | compiled | idna-3.20/ |
| certifi | 2026.10.23 | MPL-2.0 (unmodified; source: https://github.com/certifi/python-certifi) | compiled + cacert.pem | certifi-2026.10.23/ |
| typing_extensions | 4.16.0 | PSF-2.0 | compiled | typing_extensions-4.16.0/ |
| keyring | 25.7.0 | MIT | compiled | keyring-25.7.0/ |
| jaraco.classes / jaraco.context / jaraco.functools | 3.4.0 / 6.1.2 / 4.6.0 | MIT | compiled | jaraco*/ |
| more-itertools | 11.2.1 | MIT | compiled | more_itertools-11.2.1/ |
| SecretStorage | 3.5.0 | BSD-3-Clause | compiled | secretstorage-3.5.0/ |
| jeepney | 0.9.0 | MIT | compiled | jeepney-0.9.0/ |
| cryptography (incl. statically linked OpenSSL 4.0.3) | 50.0.2 | Apache-2.0 OR BSD-3-Clause; OpenSSL Apache-2.0 | shared library `_rust.so` | cryptography-50.0.2/, OpenSSL/ |
| cffi backend | 2.1.1 | MIT-0 | shared library | cffi-2.1.1/ |
| zstandard | 0.25.0 | BSD-3-Clause | shared library | zstandard-0.25.0/ |
| OpenSSL (libssl, libcrypto) | 3.5.7 (Debian 13) | Apache-2.0 | shared libraries | OpenSSL/, debian-libssl3t64/ |
| libffi | 3.4.8 | MIT | shared library | debian-libffi8/ |
| SQLite | 3.46.1 | Public domain | shared library | debian-libsqlite3-0/ |
| expat | 2.9.0 | MIT | shared library | debian-libexpat1/ |
| bzip2 | 1.0.8 | bzip2 licence | shared library | debian-libbz2-1.0/ |
| xz (liblzma) | 5.8.1 | 0BSD / public domain | shared library | debian-liblzma5/ |
| libuuid (util-linux) | 2.41.5 | BSD-3-Clause | shared library | debian-libuuid1/ |
| zstd (libzstd) | 1.5.7 | BSD-3-Clause | shared library | debian-libzstd1/ |

Not bundled (system prerequisites of the user's Debian installation): glibc, libstdc++, X11/xcb, EGL/GL, D-Bus, fontconfig/freetype, GTK 3 (optional theme), CUPS (optional printing).

## Licence texts (MIT, BSD, MIT-0) reproduced verbatim from the installed packages

### httpx 0.28.1 (BSD-3-Clause)

```text
Copyright © 2019, [Encode OSS Ltd](https://www.encode.io/).
All rights reserved.

Redistribution and use in source and binary forms, with or without modification, are permitted provided that the following conditions are met:

* Redistributions of source code must retain the above copyright notice, this list of conditions and the following disclaimer.

* Redistributions in binary form must reproduce the above copyright notice, this list of conditions and the following disclaimer in the documentation and/or other materials provided with the distribution.

* Neither the name of the copyright holder nor the names of its contributors may be used to endorse or promote products derived from this software without specific prior written permission.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS" AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT HOLDER OR CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.
```

### httpcore 1.0.9 (BSD-3-Clause)

```text
Copyright © 2020, [Encode OSS Ltd](https://www.encode.io/).
All rights reserved.

Redistribution and use in source and binary forms, with or without
modification, are permitted provided that the following conditions are met:

* Redistributions of source code must retain the above copyright notice, this
  list of conditions and the following disclaimer.

* Redistributions in binary form must reproduce the above copyright notice,
  this list of conditions and the following disclaimer in the documentation
  and/or other materials provided with the distribution.

* Neither the name of the copyright holder nor the names of its
  contributors may be used to endorse or promote products derived from
  this software without specific prior written permission.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS"
AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE
IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE
DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT HOLDER OR CONTRIBUTORS BE LIABLE
FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL
DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR
SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER
CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY,
OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE
OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.
```

### h11 0.16.0 (MIT)

```text
The MIT License (MIT)

Copyright (c) 2016 Nathaniel J. Smith <njs@pobox.com> and other contributors

Permission is hereby granted, free of charge, to any person obtaining
a copy of this software and associated documentation files (the
"Software"), to deal in the Software without restriction, including
without limitation the rights to use, copy, modify, merge, publish,
distribute, sublicense, and/or sell copies of the Software, and to
permit persons to whom the Software is furnished to do so, subject to
the following conditions:

The above copyright notice and this permission notice shall be
included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND
NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE
LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION
OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION
WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
```

### anyio 4.16.0 (MIT)

```text
The MIT License (MIT)

Copyright (c) 2018 Alex Grönholm

Permission is hereby granted, free of charge, to any person obtaining a copy of
this software and associated documentation files (the "Software"), to deal in
the Software without restriction, including without limitation the rights to
use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of
the Software, and to permit persons to whom the Software is furnished to do so,
subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS
FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR
COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER
IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN
CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
```

### idna 3.20 (BSD-3-Clause)

```text
BSD 3-Clause License

Copyright (c) 2013-2026, Kim Davies and contributors.
All rights reserved.

Redistribution and use in source and binary forms, with or without
modification, are permitted provided that the following conditions are
met:

1. Redistributions of source code must retain the above copyright
   notice, this list of conditions and the following disclaimer.

2. Redistributions in binary form must reproduce the above copyright
   notice, this list of conditions and the following disclaimer in the
   documentation and/or other materials provided with the distribution.

3. Neither the name of the copyright holder nor the names of its
   contributors may be used to endorse or promote products derived from
   this software without specific prior written permission.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS
"AS IS" AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT
LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR
A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT
HOLDER OR CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL,
SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED
TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR
PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF
LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING
NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS
SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.
```

### keyring 25.7.0 (MIT)

```text
MIT License

Copyright (c) 2025 <copyright holders>

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and
associated documentation files (the "Software"), to deal in the Software without restriction, including
without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the
following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial
portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT
LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO
EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER
IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE
USE OR OTHER DEALINGS IN THE SOFTWARE.
```

### jaraco.classes 3.4.0 (MIT)

```text
Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to
deal in the Software without restriction, including without limitation the
rights to use, copy, modify, merge, publish, distribute, sublicense, and/or
sell copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING
FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS
IN THE SOFTWARE.
```

### jaraco.context 6.1.2 (MIT)

```text
MIT License

Copyright (c) 2026 <copyright holders>

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and
associated documentation files (the "Software"), to deal in the Software without restriction, including
without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the
following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial
portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT
LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO
EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER
IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE
USE OR OTHER DEALINGS IN THE SOFTWARE.
```

### jaraco.functools 4.6.0 (MIT)

```text
MIT License

Copyright (c) 2026 <copyright holders>

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and
associated documentation files (the "Software"), to deal in the Software without restriction, including
without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the
following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial
portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT
LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO
EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER
IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE
USE OR OTHER DEALINGS IN THE SOFTWARE.
```

### more-itertools 11.2.1 (MIT)

```text
Copyright (c) 2012 Erik Rose

Permission is hereby granted, free of charge, to any person obtaining a copy of
this software and associated documentation files (the "Software"), to deal in
the Software without restriction, including without limitation the rights to
use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies
of the Software, and to permit persons to whom the Software is furnished to do
so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

### SecretStorage 3.5.0 (BSD-3-Clause)

```text
Copyright 2012-2025 Dmitry Shachnev <mitya57@gmail.com>
All rights reserved.

Redistribution and use in source and binary forms, with or without
modification, are permitted provided that the following conditions are met:

1. Redistributions of source code must retain the above copyright notice, this
   list of conditions and the following disclaimer.
2. Redistributions in binary form must reproduce the above copyright notice,
   this list of conditions and the following disclaimer in the documentation
   and/or other materials provided with the distribution.
3. Neither the name of the University nor the names of its contributors may be
   used to endorse or promote products derived from this software without
   specific prior written permission.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS" AND
ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED
WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE
DISCLAIMED. IN NO EVENT SHALL THE REGENTS OR CONTRIBUTORS BE LIABLE FOR ANY
DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES
(INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES;
LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON
ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT
(INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS
SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.
```

### jeepney 0.9.0 (MIT)

```text
The MIT License (MIT)

Copyright (c) 2017 Thomas Kluyver

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
```

### cryptography 50.0.2 (Apache-2.0 OR BSD-3-Clause)

```text
Copyright (c) Individual contributors.
All rights reserved.

Redistribution and use in source and binary forms, with or without
modification, are permitted provided that the following conditions are met:

    1. Redistributions of source code must retain the above copyright notice,
       this list of conditions and the following disclaimer.

    2. Redistributions in binary form must reproduce the above copyright
       notice, this list of conditions and the following disclaimer in the
       documentation and/or other materials provided with the distribution.

    3. Neither the name of PyCA Cryptography nor the names of its contributors
       may be used to endorse or promote products derived from this software
       without specific prior written permission.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS" AND
ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED
WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE
DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT OWNER OR CONTRIBUTORS BE LIABLE FOR
ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES
(INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES;
LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON
ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT
(INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS
SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.
```

### cffi 2.1.1 (MIT-0)

```text
Except when otherwise stated (look for LICENSE files in directories or
information at the beginning of each file) all software and
documentation is licensed as follows: 

    MIT No Attribution

    Permission is hereby granted, free of charge, to any person 
    obtaining a copy of this software and associated documentation 
    files (the "Software"), to deal in the Software without 
    restriction, including without limitation the rights to use, 
    copy, modify, merge, publish, distribute, sublicense, and/or 
    sell copies of the Software, and to permit persons to whom the 
    Software is furnished to do so.

    THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS 
    OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, 
    FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL 
    THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER 
    LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING 
    FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER 
    DEALINGS IN THE SOFTWARE.
```

### pycparser 3.12 (BSD-3-Clause)

```text
pycparser -- A C parser in Python

Copyright (c) 2008-2027, Eli Bendersky
All rights reserved.

Redistribution and use in source and binary forms, with or without modification,
are permitted provided that the following conditions are met:

* Redistributions of source code must retain the above copyright notice, this 
  list of conditions and the following disclaimer.
* Redistributions in binary form must reproduce the above copyright notice, 
  this list of conditions and the following disclaimer in the documentation 
  and/or other materials provided with the distribution.
* Neither the name of the copyright holder nor the names of its contributors may 
  be used to endorse or promote products derived from this software without 
  specific prior written permission.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS" AND 
ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED 
WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE 
DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT HOLDER OR CONTRIBUTORS BE 
LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR 
CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE 
GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) 
HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT 
LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT 
OF THE USE OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.
```
