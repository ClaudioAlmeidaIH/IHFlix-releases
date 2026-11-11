# IH Flix — versões e configuração

Este repositório guarda o que as TV boxes do IH Flix (app de Android TV das cabines do
Instituto Homem) leem pela internet. O código-fonte fica em outro repositório, privado.

## config.json — canais, assuntos e tempos

As boxes leem o arquivo [`config.json`](config.json) a cada 30 minutos. Para mudar algo no
app **sem instalar nada nas boxes**, edite esse arquivo aqui no GitHub (ícone de lápis →
"Commit changes"). A mudança chega às boxes em até 35 minutos.

| Campo | O que é |
|---|---|
| `canais` | Canais do YouTube de onde vêm os vídeos. `channelId` começa com `UC` (na página do canal: código-fonte → procure `externalId`). `porAssunto: false` deixa o canal fora das fileiras por assunto. |
| `playlists` | Playlists extras para trazer mais vídeos (o YouTube só entrega os 15 mais recentes de cada canal ou playlist). `playlistId` é o trecho depois de `list=` no endereço. |
| `assuntos` | Fileiras por assunto. Cada vídeo entra na primeira fileira, de cima para baixo, que tiver uma das `palavrasChave` no título (maiúsculas e acentos não importam). |
| `mostrarFileirasDosCanais` | `true` mostra também uma fileira por canal. Vem `false` para o catálogo não repetir os mesmos vídeos. |
| `tituloOutros` | Fileira dos vídeos que não combinam com nenhum assunto. |
| `mostrarMaisAssistidos`, `tituloMaisAssistidos`, `maisAssistidosPorCanal`, `maisAssistidosVariar` | Primeira fileira, com os mais vistos de cada canal. |
| `mostrarShorts`, `tituloShorts`, `shortsNoModoAutomatico` | Fileira de Shorts. |
| `inatividadeSegundos` | Segundos sem tecla até os vídeos começarem sozinhos. |
| `contagemVisivelSegundos` | O aviso "os vídeos começam sozinhos" só aparece quando faltam esses segundos (0 esconde). |
| `pausaMaximaMinutos` | Vídeo pausado volta a tocar depois desse tempo. |
| `duracaoMaximaAutomaticoMinutos` | Vídeos mais longos que isso são pulados quando a TV toca sozinha (0 desliga). |
| `lembreteIntervaloSegundos`, `lembreteDuracaoSegundos` | Aviso "pegue o controle e aperte OK" (intervalo 0 desliga). |
| `painelSegundos`, `dicaSegundos` | Tempo do painel de vídeos (tecla ▼) e da dica de teclas. |
| `atualizacaoHoras` | De quantas em quantas horas a lista de vídeos é atualizada. |

Cuidados ao editar:

- Mantenha as aspas, vírgulas e colchetes. Se o arquivo ficar com erro de formato, as boxes o
  ignoram e continuam com a última configuração boa.
- Um campo apagado ou com valor inválido volta ao padrão embutido no app.

## Versões do app (APK)

- **Baixar a versão atual:** [ihflix.apk](https://github.com/ClaudioAlmeidaIH/IHFlix-releases/releases/latest/download/ihflix.apk)
- **Todas as versões:** aba [Releases](https://github.com/ClaudioAlmeidaIH/IHFlix-releases/releases)

As boxes procuram versão nova ao serem ligadas e a cada 6 horas.
