# VoidZone — Releases

Este repositório é destinado exclusivamente à **distribuição pública das versões do VoidZone para Windows**. Os instaladores e os metadados usados pelo atualizador automático são publicados na área [Releases](https://github.com/Gigslol/VoidZone/releases).

O código-fonte do aplicativo não é distribuído neste repositório.

## Versão estável atual

**VoidZone 1.1.2 — Windows**

A versão 1.1.2 é a primeira Release pública preparada para o fluxo de atualização automática.

## Instalação

1. Abra a [Release mais recente](https://github.com/Gigslol/VoidZone/releases/latest).
2. Baixe o arquivo `VoidZone-Setup-<versão>.exe` na seção **Assets**.
3. Execute o instalador e conclua a instalação.

Se você utilizava uma versão anterior sem canal público de atualização, instale a versão 1.1.2 manualmente uma última vez para fazer a transição.

**Faça cópias de segurança do trabalho importante antes de instalar ou atualizar.** O instalador não deve apagar os dados do usuário, mas a cópia de segurança continua sendo a proteção recomendada.

## Atualizações automáticas

Em uma instalação configurada para este repositório, o VoidZone:

- verifica novas versões ao abrir e a cada 6 horas enquanto permanecer aberto;
- baixa automaticamente somente Releases estáveis e mais recentes;
- não instala versões de pré-lançamento nem faz downgrade;
- exibe uma notificação quando o download termina;
- instala a atualização ao fechar o aplicativo, sem forçar reinício.

Se não houver conexão, a tentativa é registrada no log local e uma nova verificação ocorre no próximo ciclo. Não são necessários tokens ou contas de cliente para baixar as atualizações públicas.

## Arquivos publicados

Cada versão estável inclui três arquivos na seção **Assets** da Release:

| Arquivo | Finalidade |
| --- | --- |
| `VoidZone-Setup-<versão>.exe` | Instalador Windows do VoidZone. |
| `latest.yml` | Manifesto da versão estável mais recente, incluindo tamanho e SHA-512 do instalador. |
| `VoidZone-Setup-<versão>.exe.blockmap` | Mapa de blocos para otimizar downloads diferenciais entre versões. |

O manifesto `latest.yml` precisa sempre apontar para a Release estável mais recente. Instaladores e manifestos de uma mesma versão não devem ser substituídos após a publicação; correções devem usar uma nova versão semver.

## Integridade e assinatura digital

O atualizador verifica o SHA-512 informado pelo manifesto antes de aceitar o download.

**O instalador atual não possui assinatura digital Authenticode.** O Windows SmartScreen pode apresentar um aviso de origem desconhecida. Baixe os arquivos somente desta área oficial de Releases e confira se a versão é a pretendida.

## Manutenção de Releases

Para cada nova versão:

1. Incremente a versão seguindo semver (`MAJOR.MINOR.PATCH`).
2. Gere o instalador com o canal `Gigslol/VoidZone` configurado no build.
3. Publique o instalador e o blockmap e, em seguida, o manifesto atualizado.
4. Marque a Release como estável, sem selecionar pre-release.
5. Preserve os artefatos das versões anteriores para permitir downloads diferenciais e referência histórica.

Contas, licenciamento e cobrança são responsabilidades do produto e de seu backend, separadas deste canal público de distribuição.
