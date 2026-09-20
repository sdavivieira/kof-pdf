# kof-pdf

Biblioteca para gerar PDF diretamente com Kof, sem bibliotecas Java externas.

Requisitos: Kof `0.4.x-beta` e target JVM.

## Executar

```powershell
kof run main.kf
kof check main.kf --target jvm
```

`run` gera `relatorio.pdf`; `check` apenas valida o código.

## Usar no projeto

Copie a pasta `pdf/` para a raiz do seu projeto:

```text
meu-projeto/
├── main.kf
└── pdf/
```

```kof
import pdf.PdfDocument
main() { var pdf = PdfDocument() }
```

## API

| Comando | Função |
| --- | --- |
| `PdfDocument()` | cria o documento |
| `.title(texto[, x, y])` / `.text(texto[, x, y])` | adiciona título ou texto |
| `.grid(colunas)` | cria um grid com a quantidade informada de colunas |
| `.save(caminho)` | salva o PDF |
| `.header(lista)` / `.row(lista)` / `.rows(listas)` | adiciona cabeçalho ou linhas ao grid |
| `.widths(lista)` | define a largura de cada coluna |
| `.fontSize()` / `.fontColor()` / `.width()` / `.align()` | configura um texto |
| `TextStyle()` | cria um estilo de texto reutilizável |
| `GridStyle()` | configura altura, padding, bordas, fundos e textos do grid |
| `PdfColor(r, g, b)` / `PdfColor("#RRGGBB")` | cria uma cor |
| `TextAlign.left`, `.center`, `.right` | define o alinhamento |

Veja [`main.kf`](main.kf) para a demonstração completa.

Limitações: uma página A4, Helvetica, WinAnsi e sem quebra automática de texto ou página.
Licença: MIT — consulte [`LICENSE`](LICENSE).
