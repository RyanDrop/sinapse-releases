# Sinapse: versões para Windows

Este repositório guarda somente as versões publicadas do **Sinapse**, um segundo cérebro para o desktop. Aqui estão o instalador e as informações que o próprio aplicativo usa para saber se há versão nova. O código-fonte não fica aqui.

- [Baixar a versão mais recente](https://github.com/RyanDrop/sinapse-releases/releases/latest)
- [Todas as versões](https://github.com/RyanDrop/sinapse-releases/releases)

## O que é o Sinapse

O Sinapse organiza notas, reuniões, áudios, documentos e projetos em pastas comuns do seu computador, chamadas de cérebros. Um mapa mostra como as coisas se ligam. Há um quadro Kanban por projeto e o Córtex, onde agentes de IA trabalham nas tarefas.

Cada cérebro é uma pasta que você escolhe. O aplicativo fica em outro lugar. Instalar, atualizar ou remover o Sinapse nunca mexe nas pastas dos seus cérebros.

## Requisitos

- Windows 10 ou 11, 64 bits (x64).
- Cerca de 1 GB livre para o aplicativo. Cada atualização baixa o instalador inteiro, de cerca de 330 MB, e mantém a versão anterior até a próxima.
- Internet só para baixar, atualizar e usar recursos que você conectar (backup no GitHub, calendários, agentes de IA). As notas e o mapa funcionam sem internet.

## Instalar

1. Baixe `Sinapse-<versão>-Setup.exe` na [versão mais recente](https://github.com/RyanDrop/sinapse-releases/releases/latest).
2. Abra o arquivo. A instalação é só para o seu usuário e não pede administrador.
3. O aplicativo vai para `%LOCALAPPDATA%\Programs\Sinapse`. Os atalhos ficam no menu Iniciar, na pasta **Sinapse**.

### O aviso "O Windows protegeu o computador"

O instalador ainda não tem assinatura digital paga. Por isso, na primeira vez, o SmartScreen do Windows pode mostrar esse aviso. Para seguir, clique em **Mais informações** e depois em **Executar assim mesmo**.

Antes, se quiser, confira se o arquivo é o publicado aqui. Cada versão traz um arquivo `latest.yml` com o `sha512` do instalador. No PowerShell, na pasta do download:

```powershell
$arquivo = "Sinapse-0.1.1-Setup.exe"   # troque pelo nome que você baixou
$bytes = [IO.File]::ReadAllBytes((Resolve-Path $arquivo))
[Convert]::ToBase64String([Security.Cryptography.SHA512]::Create().ComputeHash($bytes))
```

O resultado precisa ser igual à linha `sha512:` do `latest.yml` da mesma versão.

No Windows 11 com o **Controle Inteligente de Aplicativos** ligado, um programa sem assinatura pode ser bloqueado sem a opção de seguir. Nesse caso, o Sinapse ainda não pode ser instalado nesse computador.

## Atualizações

O Sinapse instalado procura versões novas sozinho.

- **Quando procura:** 30 segundos depois de abrir e, depois, a cada 6 horas. Em **Configurações › Atualizações** há o botão **Procurar agora**.
- **O que consulta:** só o arquivo `latest.yml` da versão mais recente deste repositório, por um link público do GitHub. Não envia dados seus, não usa conta nem token e não tem telemetria. O GitHub, como qualquer site, vê o endereço IP de quem baixa.
- **Como avisa:** um aviso fixo no topo do aplicativo, com o número da versão. Ele fica até você decidir. **Agora não** esconde o aviso até sair uma versão mais nova.
- **Quando baixa:** só quando você clica em **Baixar e atualizar**. O progresso aparece no aviso, e dá para cancelar.
- **Conferência:** antes de instalar, o aplicativo compara o `sha512` do arquivo baixado com o publicado. Se não bater, recusa e mantém a versão que você usa.
- **Quando instala:** você escolhe **Reiniciar agora** ou **Ao fechar o Sinapse**. O instalador roda sem janelas, espera o aplicativo fechar, instala a versão nova ao lado da atual e só então troca.
- **Sem internet:** o aplicativo abre normalmente. A falha aparece só em **Configurações › Atualizações**, e ele tenta de novo mais tarde.

Só entram as versões estáveis. Versões marcadas como pré-lançamento neste repositório não são oferecidas pelo aplicativo.

### O que uma atualização toca e o que não toca

| Toca | Não toca |
|---|---|
| `%LOCALAPPDATA%\Programs\Sinapse\releases\` (as versões do aplicativo) | As pastas dos seus cérebros, incluindo `.sinapse\` |
| `%LOCALAPPDATA%\Programs\Sinapse\updates\` (o instalador baixado, apagado depois) | `%APPDATA%\Sinapse` (lista de cérebros, preferências e credenciais protegidas pelo Windows) |
| Os atalhos do menu Iniciar | Seus repositórios do GitHub e o backup |

Ficam guardadas a versão atual e a anterior. As mais antigas são removidas na troca.

### Voltar à versão anterior

Se uma versão nova der problema, feche o Sinapse e use o atalho **Sinapse › Restaurar versão anterior** no menu Iniciar. Seus cérebros não mudam.

### Se a troca for interrompida

A versão nova é instalada numa pasta própria e só vira a ativa no último passo. Se faltar energia ou o instalador falhar antes disso, a versão anterior continua sendo a que abre.

## Desinstalar

Use **Configurações do Windows › Aplicativos › Sinapse › Desinstalar** ou o atalho **Desinstalar Sinapse**. A remoção apaga só os arquivos do aplicativo e os instaladores baixados por ele. As pastas dos cérebros e `%APPDATA%\Sinapse` ficam.

## Arquivos de cada versão

Cada versão tem a etiqueta `v<versão>`, por exemplo `v0.1.1`, e dois arquivos:

| Arquivo | Para quê |
|---|---|
| `Sinapse-<versão>-Setup.exe` | O instalador. Serve para instalar do zero e para atualizar. |
| `latest.yml` | Versão, tamanho, data e `sha512` do instalador. É o que o aplicativo lê para saber se há versão nova. |

O formato do `latest.yml`:

```yaml
version: 0.1.1
files:
  - url: Sinapse-0.1.1-Setup.exe
    sha512: <sha512 em base64>
    size: 336014642
path: Sinapse-0.1.1-Setup.exe
sha512: <sha512 em base64>
releaseDate: '2026-11-12T12:00:00.000Z'
```

## Privacidade

O Sinapse guarda tudo no seu computador. O aplicativo só fala com serviços externos quando você conecta um, como o GitHub para backup, os calendários ou os provedores de IA. A busca por atualizações é a única consulta automática, e ela só lê o `latest.yml` público deste repositório.

## Licença

O Sinapse é gratuito para pessoas físicas, no uso pessoal e no próprio trabalho, inclusive comercial. Empresas precisam de autorização: abra uma issue ou fale com [RyanDrop](https://github.com/RyanDrop). O Sinapse não é código aberto. Os termos estão em [LICENSE.md](LICENSE.md).

O instalador inclui componentes de terceiros, cada um com sua própria licença. A lista está em [TERCEIROS.md](TERCEIROS.md).

## Contato

Para relatar um problema ou sugerir algo, abra uma [issue](https://github.com/RyanDrop/sinapse-releases/issues) neste repositório. Diga a versão (em **Configurações › Atualizações**) e o que aconteceu. Não inclua conteúdo dos seus cérebros, senhas nem tokens.
