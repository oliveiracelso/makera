# Makera / Carvera workspace

Workspace de desenvolvimento para o ecossistema da CNC [Makera Carvera](https://www.makera.com), organizado como meta-repositório com submodules.

## Edição própria do controller

A branch [`custom`](https://github.com/oliveiracelso/Carvera_Controller/tree/custom) do fork é a **edição própria** do Carvera Controller: o `develop` da comunidade mais todas as melhorias desenvolvidas aqui, integradas e testadas em conjunto (270 testes unitários passando) —

- correção do empacotamento (`build-backend`)
- tradução pt-BR completa (424 strings)
- limites de buffer do MDI + envio serializado (lock)
- flow control de comandos (evita desconexões em rajadas)
- cronômetro corrigido após abort + desconexão
- checagem de atualização via API de releases do GitHub
- ângulo de rotação do WCS na barra superior

Além disso, a edição tem features próprias: botões de jog no estilo Super Nintendo (X azul, Y verde, A vermelho, Z amarelo).

**Download:** [Windows x64 (.exe portátil)](https://github.com/oliveiracelso/Carvera_Controller/releases/tag/v2026.8.8)

Cada melhoria também foi submetida individualmente ao upstream (PRs abaixo); conforme forem aceitas, a `custom` é rebaseada para conter apenas o delta.

## Estrutura

| Submodule | Origem | Descrição |
|---|---|---|
| [`Carvera_Controller`](https://github.com/oliveiracelso/Carvera_Controller) | fork de [Carvera-Community](https://github.com/Carvera-Community/Carvera_Controller) | **Repositório principal de trabalho** — controller comunitário (Python/Kivy), onde as contribuições são desenvolvidas |
| [`Carvera_Community_Firmware`](https://github.com/Carvera-Community/Carvera_Community_Firmware) | Carvera-Community | Firmware comunitário (referência para limites de protocolo/buffers) |
| [`CarveraController`](https://github.com/MakeraInc/CarveraController) | MakeraInc | Controller oficial (referência/comparação) |
| [`CarveraFirmware`](https://github.com/MakeraInc/CarveraFirmware) | MakeraInc | Firmware oficial (referência) |
| [`CarveraProfiles`](https://github.com/MakeraInc/CarveraProfiles) | MakeraInc | Perfis de ferramentas e materiais |
| [`MakeraCAM`](https://github.com/MakeraInc/MakeraCAM) | MakeraInc | Rastreador de issues do CAM oficial |
| [`updates`](https://github.com/MakeraInc/updates) | MakeraInc | Histórico de atualizações |

## Clonar

```bash
git clone --recursive https://github.com/oliveiracelso/makera.git
```

## Ambiente de desenvolvimento (Carvera_Controller)

- Python 3.12 via [uv](https://docs.astral.sh/uv/): `uv venv --python 3.12 .venv` dentro de `Carvera_Controller/`
- Dependências: `uv pip install -p .venv "kivy[base]>=2.3.1,<3" certifi "pyserial>=3.5,<4" "pyquicklz>=1.4.1,<2" "hid>=1.0.7,<2" "ezdxf>=1.3,<2"` (o `pyquicklz` exige MSVC Build Tools no Windows — sem wheel pré-compilado)
- Rodar: `.venv/Scripts/python -m carveracontroller`
- Fluxo upstream: issue-first, PRs contra a branch `develop` de Carvera-Community/Carvera_Controller

## Contribuições abertas (2026-08-08)

| PR | Issue | Tema |
|---|---|---|
| [#721](https://github.com/Carvera-Community/Carvera_Controller/pull/721) | #719 | `build-backend` ausente no pyproject.toml |
| [#722](https://github.com/Carvera-Community/Carvera_Controller/pull/722) | #720 | Tradução pt-BR completa (424 strings) |
| [#723](https://github.com/Carvera-Community/Carvera_Controller/pull/723) | #718 | Limites de buffer do MDI + lock de envio |
| [#724](https://github.com/Carvera-Community/Carvera_Controller/pull/724) | #710 | Flow control de comandos (anti-desconexão) |
| [#725](https://github.com/Carvera-Community/Carvera_Controller/pull/725) | #712 | Cronômetro após desconexão |
| [#726](https://github.com/Carvera-Community/Carvera_Controller/pull/726) | #652 | Update check via API de releases do GitHub |
| [#727](https://github.com/Carvera-Community/Carvera_Controller/pull/727) | #637 | Ângulo de rotação do WCS na top bar |
