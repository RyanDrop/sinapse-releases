# Componentes de terceiros no instalador do Sinapse

O instalador do Sinapse para Windows inclui os componentes abaixo. Cada um segue a sua própria licença, e nada na [licença do Sinapse](LICENSE.md) restringe os direitos que elas garantem. Os textos completos das licenças vão junto com a instalação, nos locais indicados.

Lista conferida em 12/11/2026, no pacote da versão 0.1.0. Ela precisa ser revista a cada versão que mudar as dependências. A interface e o núcleo foram conferidos no build do commit `a2adc7b`.

## Aplicativo e runtime

| Componente | Licença | Onde está o texto na instalação |
|---|---|---|
| Electron 45 (Chromium e Node.js) | MIT; Chromium e Node.js com as licenças listadas pelo projeto | `LICENSE` e `LICENSES.chromium.html`, na pasta da versão |
| Python 3.14 (runtime privado dos workers) | PSF License | `resources/workers/python/LICENSE.txt` |
| Git para Windows (MinGit 2.56.0.4) | GPL versão 2 | `resources/git/LICENSE.txt` |
| NSIS 3.13 (gerador do instalador) | zlib/libpng | `NSIS-LICENSE.txt`, na pasta de instalação |

**Git para Windows:** o MinGit vai sem alterações, como distribuído pelo projeto. O código-fonte de cada versão está em <https://github.com/git-for-windows/git/releases>, na etiqueta da versão `v2.56.0.windows.4`.

## Bibliotecas do aplicativo desktop

| Pacote | Versão | Licença |
|---|---|---|
| fast-xml-parser | 5.11.2 | MIT |
| ical.js | 2.2.1 | MPL-2.0 |

**ical.js:** o código-fonte desta versão está em <https://github.com/kewisch/ical.js>.

## Workers de gravação, transcrição e documentos (Python)

As licenças são as declaradas por cada pacote. O texto completo de cada uma fica em `resources/workers/python/Lib/site-packages/<pacote>.dist-info/`.

| Pacote | Versão | Licença |
|---|---|---|
| annotated-doc | 0.0.5 | MIT |
| annotated-types | 0.8.0 | MIT |
| anyio | 4.15.1 | MIT |
| av (PyAV) | 18.1.0 | BSD-3-Clause; as bibliotecas do FFmpeg que vêm junto seguem a licença do FFmpeg |
| click | 8.5.0 | BSD-3-Clause |
| colorama | 0.4.6 | BSD |
| ctranslate2 | 4.8.3 | MIT |
| fastapi | 0.149.0 | MIT |
| faster-whisper | 1.2.1 | MIT |
| filelock | 4.2.4 | MIT |
| flatbuffers | 25.12.19 | Apache-2.0 |
| fsspec | 2026.9.0 | BSD-3-Clause |
| h11 | 0.16.0 | MIT |
| hf-xet | 1.7.0 | Apache-2.0 |
| httpcore2 | 2.15.1 | BSD-3-Clause |
| httpx2 | 2.15.1 | BSD-3-Clause |
| huggingface-hub | 2.2.0 | Apache-2.0 |
| idna | 3.20 | BSD-3-Clause |
| numpy | 2.5.4 | BSD-3-Clause e outras, listadas pelo projeto |
| onnxruntime | 1.31.0 | MIT |
| opentelemetry-api | 1.45.1 | Apache-2.0 |
| packaging | 26.3 | Apache-2.0 ou BSD-2-Clause |
| protobuf | 7.36.2 | BSD-3-Clause |
| PyAudioWPatch | 0.2.12.9 | Apache-2.0 |
| pydantic | 2.14.1 | MIT |
| pydantic-core | 2.50.1 | MIT |
| pypdf | 6.21.1 | BSD-3-Clause |
| PyYAML | 6.0.3 | MIT |
| starlette | 1.9.0 | BSD-3-Clause |
| tokenizers | 0.23.3 | Apache-2.0 |
| tqdm | 4.70.1 | MPL-2.0 e MIT |
| truststore | 0.10.5 | MIT |
| typing-extensions | 4.16.0 | PSF-2.0 |
| typing-inspection | 0.4.4 | MIT |
| tzdata | 2026.4 | Apache-2.0 |
| uvicorn | 0.54.0 | BSD-3-Clause |

## Modelos de transcrição

Os modelos não vêm no instalador. Você os baixa em **Configurações › Transcrição**, e a tela mostra a licença de cada um antes do download. Os modelos Whisper são da OpenAI, sob a licença MIT.

## Interface (Angular)

Bibliotecas que entram no código da interface, conforme o arquivo de licenças gerado pelo build do Angular. O texto completo de cada uma fica em `resources/licenses/interface.txt`, na pasta da versão.

| Pacote | Versão | Licença |
|---|---|---|
| @angular/cdk | 21.2.14 | MIT |
| @angular/common, core, forms, platform-browser, router | 21.2.25 | MIT |
| @kurkle/color | 0.3.4 | MIT |
| @xmldom/xmldom | 0.8.15 | MIT |
| @xterm/xterm | 6.0.0 | MIT |
| @xterm/addon-fit | 0.11.0 | MIT |
| base64-js | 1.5.1 | MIT |
| chart.js | 4.6.1 | MIT |
| d3-array, d3-brush, d3-color, d3-dispatch, d3-drag, d3-force, d3-interpolate, d3-quadtree, d3-selection, d3-timer, d3-transition, d3-zoom | 3.0.0 a 3.2.4 | ISC |
| d3-ease | 3.0.1 | BSD-3-Clause |
| dingbat-to-unicode | 1.0.2 | BSD-2-Clause |
| fflate | 0.8.3 | MIT |
| highlight.js | 11.12.0 | BSD-3-Clause |
| jszip | 3.10.2 | MIT ou GPL-3.0-or-later, à escolha; o Sinapse usa sob a MIT |
| lop | 0.4.2 | BSD-2-Clause |
| mammoth | 1.13.0 | BSD-2-Clause |
| marked | 18.1.1 | MIT |
| option | 0.2.4 | BSD-2-Clause |
| pdfjs-dist (pdf.js) | 6.4.299 | Apache-2.0 |
| read-excel-file | 9.3.12 | MIT |
| rxjs | 7.8.2 | Apache-2.0 |
| tslib | 2.8.1 | 0BSD |
| underscore | 1.13.8 | MIT |
| worker-f | 0.1.21 | MIT |
| xmlbuilder | 10.1.1 | MIT |

## Fontes

Todas sob a SIL Open Font License 1.1. O texto completo, com o aviso de cada família, fica em `resources/licenses/fontes.txt`.

| Fonte | Autores | Licença |
|---|---|---|
| DM Sans | The DM Sans Project Authors | OFL 1.1 |
| DM Mono | The DM Mono Project Authors | OFL 1.1 |
| Sinapse Sans | Versão modificada da Baloo 2 (The Baloo 2 Project Authors), em subconjunto latino e com outro nome | OFL 1.1 |

A Sinapse Sans continua sob a OFL, como a licença exige de toda versão modificada. Ela não é vendida separadamente.

## Núcleo (Go)

Módulos compilados no `sinapse-core.exe`, conforme a lista do próprio binário. O texto completo de cada licença fica em `resources/licenses/nucleo-go.txt`.

| Módulo | Versão | Licença |
|---|---|---|
| Go, biblioteca padrão | 1.27.0 | BSD-3-Clause |
| github.com/aymanbagabas/go-pty | 0.2.3 | MIT |
| github.com/fsnotify/fsnotify | 1.10.1 | BSD-3-Clause |
| github.com/ledongthuc/pdf | 0.0.0-20261020125853 | BSD-3-Clause |
| github.com/mattn/go-sqlite3 | 1.14.53 | MIT; o SQLite 3.54.1 que vem junto está em domínio público |
| go.yaml.in/yaml/v3 | 3.0.5 | MIT e Apache-2.0 |
| golang.org/x/crypto | 0.51.0 | BSD-3-Clause |
| golang.org/x/sys | 0.47.0 | BSD-3-Clause |
| golang.org/x/text | 0.43.0 | BSD-3-Clause |
