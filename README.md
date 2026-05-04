# NVIDIA Monitor Calibration Guide

Guia prático para ajustar cores, contraste, gamma, preto, nitidez e tempo de resposta de monitores gamer/IPS usando o **Painel de Controle NVIDIA** e o **EIZO Monitor Test**.

Este guia nasceu de um caso real com o monitor **ASUS VG279QR**, usando uma **NVIDIA GeForce RTX 2060 Super** via **DisplayPort**, mas foi organizado de forma universal para ajudar outras pessoas a ajustarem seus próprios monitores.

---

## Objetivo

Ajudar você a melhorar a imagem do monitor de forma prática, sem depender de “achismo” ou de configurações aleatórias.

O foco é encontrar um equilíbrio entre:

- preto mais forte;
- cores bonitas, sem exagero;
- branco sem estourar;
- texto legível;
- gradientes suaves;
- boa nitidez;
- baixo ghosting/rastro;
- boa experiência em jogos e uso diário.

---

## Aviso importante

Este guia **não substitui calibração profissional com colorímetro**.

Também é importante entender que um monitor **IPS/LCD não vira OLED**.  
O OLED consegue preto real porque desliga pixels individualmente. Em monitores IPS/LCD, o preto depende do backlight, então sempre existe um limite físico.

O objetivo aqui é chegar no melhor resultado visual possível **sem destruir detalhes de sombra, cores e leitura**.

---

## Equipamento usado como exemplo real

```text
Monitor: ASUS VG279QR
Tipo: Gamer / IPS
Resolução: 1920 x 1080
Taxa de atualização: 165 Hz
Conexão: DisplayPort
GPU: NVIDIA GeForce RTX 2060 Super
Uso principal: jogos e consumo de conteúdo
```

Perfil final encontrado no caso real:

```text
Painel NVIDIA > Monitor > Ajustar as configurações de cor da área de trabalho

Brilho: 50%
Contraste: 55%
Gamma: 0.95
Vibração digital: 53%
Matiz: 0°
```

Configuração física do monitor no caso real:

```text
Contraste do monitor: 78
Modo: padrão/fábrica
Adaptive-Sync / FreeSync: ativado
ELMB: desligado
Shadow Boost: desligado
Dynamic Contrast / ASCR: desligado
```

---

## Pré-requisitos

Antes de começar:

```text
[ ] Driver NVIDIA instalado
[ ] Painel de Controle NVIDIA disponível
[ ] Monitor ligado na GPU dedicada
[ ] Resolução nativa ativada
[ ] Taxa máxima do monitor ativada
[ ] HDR do Windows desligado para testes SDR
[ ] Luz Noturna desligada
[ ] Navegador com zoom em 100%
[ ] EIZO Monitor Test aberto
[ ] Teste em tela cheia com F11
```

---

## Configuração base no Painel NVIDIA

Abra:

```text
Painel de Controle NVIDIA > Monitor > Alterar resolução
```

Configure o monitor gamer assim:

```text
Resolução: resolução nativa do monitor
Taxa de atualização: maior taxa estável disponível
Formato de cor da saída: RGB
Profundidade da cor da saída: 8 bpc
Intervalo de saída dinâmica: Completo
```

Exemplo do ASUS VG279QR:

```text
Resolução: 1920 x 1080
Taxa de atualização: 165 Hz
Formato de cor da saída: RGB
Profundidade da cor da saída: 8 bpc
Intervalo de saída dinâmica: Completo
```

---

## Ajuste principal de cor

Abra:

```text
Painel de Controle NVIDIA > Monitor > Ajustar as configurações de cor da área de trabalho
```

Selecione o monitor correto e marque:

```text
Utilize configurações de cor da NVIDIA
```

Controles principais:

| Controle | O que faz | Risco se exagerar |
|---|---|---|
| Brilho | Clareia ou escurece a imagem geral | Preto lavado ou imagem escura demais |
| Contraste | Aumenta diferença entre claro e escuro | Branco estourado ou perda de detalhe |
| Gamma | Ajusta tons médios e sensação de preto | Sombra esmagada ou preto cinza |
| Vibração digital | Aumenta a intensidade das cores | Cores neon e pele artificial |
| Matiz | Muda o equilíbrio de tonalidade | Cores completamente erradas |

---

## Perfil base seguro

Comece com este perfil:

```text
Brilho: 50%
Contraste: 50% a 53%
Gamma: 1.00 a 0.97
Vibração digital: 50% a 53%
Matiz: 0°
```

Para a maioria dos monitores IPS, este é um ponto seguro.

---

## Perfil “preto forte” para IPS gamer

Use apenas se os testes confirmarem que não houve perda de detalhe:

```text
Brilho: 50%
Contraste: 55%
Gamma: 0.95
Vibração digital: 53%
Matiz: 0°
```

Esse perfil dá mais sensação de preto profundo sem exagerar demais.

Não recomendo baixar o gamma abaixo de **0.95** sem testar, porque pode esmagar sombras em jogos escuros.

---

## EIZO Monitor Test: fases do teste

Acesse:

```text
https://www.eizo.be/monitor-test/
```

Fases do teste:

| Fase | Nome no site | O que verifica |
|---|---|---|
| 1 | Test Pattern | Padrão geral de imagem |
| 2 | Defective Pixels on Black | Pixels defeituosos no preto |
| 3 | Defective Pixels on White | Pixels defeituosos no branco |
| 4 | Defective Pixels on Red | Pixels defeituosos no vermelho |
| 5 | Defective Pixels on Green | Pixels defeituosos no verde |
| 6 | Defective Pixels on Blue | Pixels defeituosos no azul |
| 7 | Uniformity | Uniformidade da tela |
| 8 | Color Distances | Separação entre tons de cor |
| 9 | Gradients | Suavidade dos degradês |
| 10 | Sharpness | Nitidez de texto e linhas |
| 11 | Viewing Angle | Estabilidade do ângulo de visão |
| 12 | Gamma | Equilíbrio dos tons médios |
| 13 | Response Time | Rastros, ghosting e fluidez |

---

## Ordem recomendada de teste

Faça primeiro estas fases:

```text
1. Test Pattern
7. Uniformity
8. Color Distances
9. Gradients
10. Sharpness
12. Gamma
13. Response Time
```

Depois, se quiser validar o monitor inteiro:

```text
2. Defective Pixels on Black
3. Defective Pixels on White
4. Defective Pixels on Red
5. Defective Pixels on Green
6. Defective Pixels on Blue
11. Viewing Angle
```

---

## Como interpretar os resultados

### Preto lavado

Sintoma:

```text
O preto parece cinza.
A imagem parece sem profundidade.
```

Correção:

```text
Reduzir Gamma levemente.
Exemplo: 1.00 > 0.97 > 0.95
```

Não exagere. Se baixar demais, você perde detalhe em sombras.

---

### Sombra esmagada

Sintoma:

```text
Áreas escuras viram blocos pretos.
Você para de ver detalhes em cenas escuras.
```

Correção:

```text
Subir Gamma.
Exemplo: 0.95 > 0.97 > 1.00
```

---

### Branco estourado

Sintoma:

```text
Áreas claras ficam todas iguais.
Nuvens, luzes e menus perdem detalhe.
```

Correção:

```text
Reduzir Contraste.
Exemplo: 55% > 53% > 51% > 50%
```

---

### Cores exageradas

Sintoma:

```text
Vermelho neon.
Verde radioativo.
Pele laranja.
Azul artificial.
```

Correção:

```text
Reduzir Vibração digital.
Exemplo: 55% > 53% > 50%
```

---

### Gradiente com faixas

Sintoma:

```text
Degradês ficam quebrados em faixas visíveis.
```

Correção:

```text
Voltar Gamma para perto de 1.00.
Reduzir Contraste.
Evitar saturação exagerada.
```

---

### Texto ruim ou com borda falsa

Sintoma:

```text
Texto parece serrilhado.
Bordas ficam artificiais.
```

Correção:

```text
Não corrigir pela NVIDIA.
Ajustar no menu físico do monitor:
Sharpness / Nitidez / VividPixel para padrão ou baixo.
```

---

### Rastro ou ghosting

Sintoma:

```text
Objetos em movimento deixam sombra ou rastro.
```

Correção:

```text
Ajustar Overdrive / Trace Free no monitor físico.
Usar valor médio.
Manter ELMB desligado se atrapalhar o brilho ou causar artefatos.
```

---

## G-SYNC / Adaptive-Sync

No Painel NVIDIA:

```text
Configurar G-SYNC
```

Configuração recomendada:

```text
[ ] Habilitar G-SYNC Compatível
[ ] Habilitar para modo janela e tela cheia
[ ] Ativar configurações do modelo de monitor selecionado
```

Se algum jogo apresentar piscadas, stutter ou comportamento estranho, teste:

```text
Habilitar apenas para modo de tela cheia
```

No monitor físico:

```text
Adaptive-Sync / FreeSync: ativado
ELMB: desligado
```

---

## Tela cheia ou janela sem borda em jogos?

Configure a gamma **no mesmo modo em que você joga**.

```text
Se joga em tela cheia exclusiva, configure no jogo em tela cheia.
Se joga em janela sem borda, configure no jogo em janela sem borda.
```

Para quem usa dois monitores, OBS, gravação e multitarefa:

```text
Janela sem borda costuma ser mais prática.
```

Para jogos competitivos ou antigos:

```text
Teste tela cheia exclusiva e compare FPS, frametime e G-SYNC.
```

---

## HDR

HDR bonito de verdade não é apenas mais saturação.

HDR depende de:

```text
Pico de brilho alto
Preto profundo
Boa gama dinâmica
Mapeamento de tons correto
Monitor realmente bom para HDR
```

Em monitores IPS comuns, HDR pode ficar bonito em alguns jogos, mas também pode deixar a imagem lavada ou inconsistente.

Recomendação:

```text
Jogos SDR: HDR do Windows desligado
Jogos HDR: ligar HDR apenas para o jogo e calibrar dentro do jogo
Edição SDR: HDR desligado
```

---

## Perfis sugeridos

### Uso geral equilibrado

```text
Brilho: 50%
Contraste: 50%
Gamma: 1.00
Vibração digital: 50%
Matiz: 0°
```

### Jogos com preto mais forte

```text
Brilho: 50%
Contraste: 55%
Gamma: 0.95
Vibração digital: 53%
Matiz: 0°
```

### Jogos mais coloridos

```text
Brilho: 50%
Contraste: 55%
Gamma: 0.95
Vibração digital: 55%
Matiz: 0°
```

Use com cuidado. Acima de 55%, algumas cores podem ficar artificiais.

### Leitura e produtividade

```text
Brilho: 50%
Contraste: 50%
Gamma: 1.00
Vibração digital: 50%
Matiz: 0°
```

---

## O que não recomendo

```text
Não usar Vibração digital acima de 60% como padrão.
Não baixar Gamma agressivamente sem testar sombras.
Não ligar Shadow Boost alto para uso geral.
Não ligar Dynamic Contrast / ASCR para calibrar.
Não usar HDR do Windows o tempo todo em monitor SDR/IPS comum.
Não tentar deixar LCD/IPS igual OLED sacrificando detalhe de sombra.
```

---

## Checklist final rápido

```text
[ ] Resolução nativa ativada
[ ] Taxa máxima ativada
[ ] RGB ativado
[ ] 8 bpc ativado
[ ] Intervalo dinâmico completo
[ ] HDR desligado para testes SDR
[ ] Luz Noturna desligada
[ ] Perfil NVIDIA aplicado
[ ] EIZO Test Pattern aprovado
[ ] Uniformity aprovada
[ ] Color Distances aprovado
[ ] Gradients sem faixas graves
[ ] Sharpness confortável
[ ] Gamma equilibrado
[ ] Response Time sem ghosting incômodo
[ ] Jogo testado no modo real de uso
```

---

## Perfil real validado: ASUS VG279QR

```text
Nome do perfil:
ASUS VG279QR — Jogos / Preto Forte / NVIDIA 0.95

Painel NVIDIA:
Brilho: 50%
Contraste: 55%
Gamma: 0.95
Vibração digital: 53%
Matiz: 0°

Alterar resolução:
1920 x 1080
165 Hz
RGB
8 bpc
Intervalo dinâmico: Completo

Monitor físico:
Contraste: 78
Modo: padrão/fábrica
Adaptive-Sync / FreeSync: ativado
ELMB: desligado
Shadow Boost: desligado
Dynamic Contrast / ASCR: desligado
```

---

## Licença

Este guia pode ser usado, adaptado e compartilhado livremente para fins pessoais, educacionais e técnicos.
