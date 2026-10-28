# CineClub – Oficina de Swift

Workshop de introdução ao desenvolvimento iOS, promovido pela **Apple Developer Academy | Mackenzie** para alunos da universidade. Neste workshop construímos o **CineClub**, um aplicativo para visualizar filmes e marcar os favoritos, usando **Swift** e **SwiftUI**.

![Gio](https://github.com/user-attachments/assets/3382209d-62ca-4ff5-abe9-ccc11190cb62)

## O app

O CineClub é "o lugar ideal para buscar, salvar e organizar seus filmes favoritos". O app tem:

- **Tela inicial** com a logo e o botão "Quero começar".
- **Filmes**: lista de filmes populares com pôster, data de lançamento e nota. Cada filme tem um botão de coração para favoritar.
- **Detalhes do filme**: pôster em destaque, nota e sinopse.
- **Favoritos**: grade com os filmes favoritados.
- **Perfil**: foto, nome e descrição do usuário.

A navegação principal é uma `TabView` com as abas Filmes, Favoritos e Perfil.

## O que você vai aprender

- Criar telas com **SwiftUI** (`VStack`, `HStack`, `ZStack`, `ScrollView`, `LazyVGrid`)
- Navegação com `NavigationStack`, `NavigationLink` e `TabView`
- Estado com `@State`
- Reaproveitamento de views (`MovieCell`, `DetailedMovieView`)
- Uso de imagens, cores e ícones (SF Symbols) com o catálogo de assets
- Pré-visualização com `#Preview`

## Como seguir o workshop

O repositório tem duas branches principais:

| Branch | Conteúdo |
|---|---|
| [`main`](https://github.com/citricgio/CineClub_SwiftWorkshop/tree/main) | **Ponto de partida.** Projeto base com assets e as telas de filmes e favoritos iniciais. É onde você desenvolve durante a oficina. |
| [`gabarito`](https://github.com/citricgio/CineClub_SwiftWorkshop/tree/gabarito) | **Código completo.** App finalizado, com as telas organizadas em pastas. Use para conferir ou tirar dúvidas. |

Travou em algum passo? Compare o seu código com o da branch `gabarito`.

## Como executar

**Requisitos**

- macOS com [Xcode](https://developer.apple.com/xcode/)
- iOS 16.0 ou superior (simulador ou aparelho)
- Swift 5

**Passos**

```bash
git clone https://github.com/citricgio/CineClub_SwiftWorkshop.git
cd CineClub_SwiftWorkshop

# para ver o app completo
git checkout gabarito

open CineClub.xcodeproj
```

No Xcode, escolha um simulador de iPhone e pressione **⌘R**.

## Estrutura do projeto (branch `gabarito`)

```
CineClub/
├── Main/
│   ├── CineClubApp.swift        # ponto de entrada do app
│   └── ContentView.swift        # NavigationStack com a tela inicial
├── Views/
│   ├── HomeView.swift           # tela inicial e TabView
│   ├── ProfileView.swift        # aba Perfil
│   ├── Movies/
│   │   ├── MoviesView.swift         # lista de filmes
│   │   ├── MovieCell.swift          # célula de um filme
│   │   └── DetailedMovieView.swift  # detalhes do filme
│   └── Favorites/
│       └── FavoriteMoviesView.swift # aba Favoritos
└── Assets.xcassets/             # logo, cores e pôsteres dos filmes
```

## Tecnologias

- Swift 5
- SwiftUI
- Xcode

## Desafio: compartilhar o estado dos favoritos

No gabarito, o coração da aba **Filmes** só muda o estado daquela tela, e a aba **Favoritos** mostra uma lista fixa. Faça com que um filme favoritado apareça na aba **Favoritos** e saia dela ao desfavoritar.

**Dica:** o estado precisa ficar fora de `MoviesView`. Pesquise por `ObservableObject` e `@EnvironmentObject` (o projeto usa iOS 16, então o `@Observable` não está disponível).

## Observações

- Os dados dos filmes são fixos no código. Não há API nem banco de dados.
- No gabarito, a aba **Favoritos** ainda não reage aos corações da aba **Filmes**. Veja o desafio acima.
