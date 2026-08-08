# Makera / Carvera workspace

Workspace de desenvolvimento para o ecossistema da CNC [Makera Carvera](https://www.makera.com), organizado como meta-repositório com submodules.

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
