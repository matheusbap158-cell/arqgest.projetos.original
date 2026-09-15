# arqGest Arquitetura — Landing page

Estúdio de arquitetura em Lavras, MG (antes D'Arco Arquitetura, renomeado para
arqGest Arquitetura). Página única em HTML/CSS/JS, sem dependências nem etapa
de build: abra `index.html` no navegador.

## Estrutura

| Caminho | O que é |
|---|---|
| `index.html` | A página inteira — marcação, estilos e scripts em um arquivo |
| `Fotos/` | Renders dos projetos |
| `Logo/` | Logotipo oficial (`arqgest-logo.png` lockup completo, `arqgest-simbolo.png` só o ícone) |
| `Instagram/` | Link do perfil oficial (`@arqgest.projetos`) |
| `Info Maps.txt` | Ficha do Google Maps — endereço, telefone e avaliações reais |
| `Modern_house_pool_at_dusk_*.mp4` | Vídeo de fundo do hero |
| `Materiais Desing System/` | Design system que rege cores, tipografia e componentes |
| `Estrutura de sessões e Texto.txt` | Copy aprovado, usado palavra por palavra |
| `serve.mjs` | Servidor estático opcional, só para pré-visualizar |

## Pré-visualizar

```bash
node serve.mjs
```

Depois abra `http://localhost:4321`.

## Decisões técnicas

- **Sem bibliotecas.** Único recurso externo: Cormorant Garamond e Manrope
  via Google Fonts, as duas famílias que o design system especifica.
- **Vídeo do hero** só carrega em telas ≥768px e sem preferência por movimento
  reduzido — são 3,5 MB que não descem no celular. A foto serve de plano base.
- **Botão de pausa** no vídeo: a WCAG 2.2.2 exige controle para movimento
  automático com mais de 5 segundos.
- **Menu mobile** aplica `inert` no restante da página enquanto aberto, para o
  foco de teclado não vazar por trás do painel.
- **Tratamento fotográfico** por filtro CSS: os renders de luz diurna fria
  recebem correção quente, para uniformizar com os de fim de tarde.
- **Logo no cabeçalho vs. rodapé.** O cabeçalho usa só `arqgest-simbolo.png`
  (compacto, legível na barra fixa de ~68–76px); o rodapé usa o lockup
  completo `arqgest-logo.png` (ícone + "arqGest" + "Projetos e Construção"),
  onde há espaço vertical para a marca inteira.

## Pendências antes de publicar

1. **Fotos sem projeto real associado.** Os 9 renders atuais (`Fotos/1–9.png`)
   não vieram com nome, endereço ou metragem de projeto — são majoritariamente
   interiores de quarto e duas fachadas residenciais. Os 3 usados no portfólio
   (`Fotos/8`, `Fotos/4`, `Fotos/6`) têm título e metragem placeholder,
   marcados `data-ficticio` no HTML. Trocar pelos dados reais quando
   disponíveis.
2. **Dados fictícios.** Buscar `data-ficticio` no HTML (9 ocorrências): número
   de projetos entregues, cidades atendidas e os nomes/metragens dos 3
   projetos do portfólio.
3. **35+ anos** vem da bio do Instagram, não de fonte interna. Confirmar.
4. **`[E-mail]`** no rodapé — nenhum e-mail veio no material novo (Instagram,
   Google Maps, design system). Preencher quando houver.
5. **Imagens.** ~22 MB de PNG. Converter para WebP/AVIF antes de ir ao ar.

## Resolvido nesta rodada

- **Nome da empresa**: D'Arco Arquitetura → arqGest Arquitetura, em todo o
  HTML (título, meta tags, textos, CTAs, rodapé).
- **Logotipo**: substituído o lockup tipográfico provisório pelos arquivos
  oficiais com transparência real (`Logo/arqgest-*.png`); favicon reativado.
- **Instagram**: `@darco.arquitetura` → `@arqgest.projetos` em todos os links.
- **Endereço e telefone**: atualizados para os dados da ficha do Google Maps
  (`Info Maps.txt`) — R. Srg. Ozório, 12, Sl. 03, Centro, Lavras-MG,
  37200-032 · (35) 99927-9396.
- **Depoimento**: preenchido com uma avaliação real do Google (Sandra Lima,
  5,0★ · 69 avaliações) — deixou de ser placeholder.
- **Fotos**: `Fotos/1–9.png` substituídas pelo material novo; alt-text e
  legendas do portfólio reescritas para bater com as imagens atuais.
