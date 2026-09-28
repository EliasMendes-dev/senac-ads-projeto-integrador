### 1. Cálculo de Aumento Salarial

```mermaid
graph TD
    A([Início]) --> B[/"ESCREVA 'INFORME O ANO ATUAL PARA O CALCULO:'"/]
    B --> C[/LEIA ano_atual/]
    C --> D{ano_atual < 2006}
    D -- Sim --> E[/"ESCREVA 'O ANO DEVE SER IGUAL OU SUPERIOR A 2006.'"/]
    E --> Z([Fim])
    
    D -- Não --> F["salario_inicial <- 1000.00<br>percentual <- 0.015<br>salario_atual <- salario_inicial + (salario_inicial * percentual)"]
    F --> G{PARA i DE 2007 ATÉ ano_atual}
    
    G -- Loop --> H["percentual <- percentual * 2<br>salario_atual <- salario_atual + (salario_atual * percentual)"]
    H --> G
    
    G -- Fim do Loop --> I[/"ESCREVA 'O SALARIO ATUAL DO FUNCIONARIO E: R$ ', salario_atual"/]
    I --> Z
```

---

### 2. Estatística de Acidentes de Trânsito

```mermaid
graph TD
    A([Início]) --> B["MAIOR_NUM_ACIDENTES <- -9999<br>MENOR_NUM_ACIDENTES <- 99999<br>TOTAL_VEICULOS <- 0<br>TOTAL_ACIDENTES <- 0<br>CIDADES_MENOS_2000 <- 0"]
    B --> C{PARA CODIGO_CIDADE DE 1 ATÉ 5}
    
    C -- Loop --> D[/"LEIA NUM_VEICULOS<br>LEIA NUM_ACIDENTES"/]
    D --> E{MENOR_NUM_ACIDENTES > NUM_ACIDENTES}
    
    E -- Sim --> F["MENOR_NUM_ACIDENTES <- NUM_ACIDENTES<br>ID_CIDADE_MENOR <- CODIGO_CIDADE"]
    E -- Não --> G{MAIOR_NUM_ACIDENTES < NUM_ACIDENTES}
    F --> G
    
    G -- Sim --> H["MAIOR_NUM_ACIDENTES <- NUM_ACIDENTES<br>ID_CIDADE_MAIOR <- CODIGO_CIDADE"]
    G -- Não --> I["TOTAL_VEICULOS <- TOTAL_VEICULOS + NUM_VEICULOS"]
    H --> I
    
    I --> J{NUM_VEICULOS < 2000}
    J -- Sim --> K["TOTAL_ACIDENTES <- TOTAL_ACIDENTES + NUM_ACIDENTES<br>CIDADES_MENOS_2000 <- CIDADES_MENOS_2000 + 1"]
    J -- Não --> L((Volta))
    K --> L
    L --> C
    
    C -- Fim do Loop --> M["MEDIA_VEICULOS <- TOTAL_VEICULOS / 5<br>MEDIA_ACIDENTES <- TOTAL_ACIDENTES / CIDADES_MENOS_2000"]
    M --> N[/"ESCREVA RESULTADOS (Médias, Maior e Menor índice)"/]
    N --> Z([Fim])
```

---

### 3. Série Numérica

```mermaid
graph TD
    A([Início]) --> B[/"LEIA NUMERO_TERMOS"/]
    B --> C{NUMERO_TERMOS <= 0}
    
    C -- Sim --> D[/"ESCREVA 'O NUMERO DE TERMOS DEVE SER MAIOR QUE ZERO.'"/]
    D --> Z([Fim])
    
    C -- Não --> E["PRIMEIRO <- 2<br>SEGUNDO <- 7<br>TERCEIRO <- 3"]
    E --> F[/"ESCREVA PRIMEIRO, SEGUNDO, TERCEIRO"/]
    F --> G["CONTADOR <- 3"]
    
    G --> H{ENQUANTO CONTADOR < NUMERO_TERMOS}
    
    H -- Loop --> I["PRIMEIRO <- PRIMEIRO * 2<br>SEGUNDO <- SEGUNDO * 3<br>TERCEIRO <- TERCEIRO * 4"]
    I --> J[/"ESCREVA PRIMEIRO, SEGUNDO, TERCEIRO"/]
    J --> K["CONTADOR <- CONTADOR + 3"]
    K --> H
    
    H -- Fim do Loop --> Z
```

---

### 4. Média de Notas de Alunos

```mermaid
graph TD
    A([Início]) --> B["TOTAL_APROVADOS <- 0<br>TOTAL_EXAME <- 0<br>TOTAL_REPROVADOS <- 0<br>MEDIA_TURMA <- 0"]
    B --> C{PARA NUMERO_ALUNO DE 1 ATÉ 6}
    
    C -- Loop --> D["MEDIA_ALUNO <- 0"]
    D --> E{PARA NUMERO_NOTA DE 1 ATÉ 2}
    
    E -- Loop --> F[/"LEIA NOTA"/]
    F --> G["MEDIA_ALUNO <- MEDIA_ALUNO + NOTA"]
    G --> E
    
    E -- Fim do Loop Interno --> H["MEDIA_ALUNO <- MEDIA_ALUNO / 2.0"]
    H --> I[/"ESCREVA 'MÉDIA DO ALUNO: ', MEDIA_ALUNO"/]
    I --> J{MEDIA_ALUNO < 3}
    
    J -- Sim --> K[/"ESCREVA 'REPROVADO'"/]
    K --> K2["TOTAL_REPROVADOS <- TOTAL_REPROVADOS + 1"]
    
    J -- Não --> L{MEDIA_ALUNO >= 3 E < 7}
    
    L -- Sim --> M[/"ESCREVA 'EXAME'"/]
    M --> M2["TOTAL_EXAME <- TOTAL_EXAME + 1"]
    
    L -- Não --> N[/"ESCREVA 'APROVADO'"/]
    N --> N2["TOTAL_APROVADOS <- TOTAL_APROVADOS + 1"]
    
    K2 --> O["MEDIA_TURMA <- MEDIA_TURMA + MEDIA_ALUNO"]
    M2 --> O
    N2 --> O
    O --> C
    
    C -- Fim do Loop Principal --> P["MEDIA_TURMA <- MEDIA_TURMA / 6"]
    P --> Q[/"ESCREVA TOTAIS E MÉDIA DA TURMA"/]
    Q --> Z([Fim])
```

---

### 5. Campeonato de Futebol

```mermaid
graph TD
    A([Início]) --> B["TOTAL_MENORES_18 <- 0<br>TOTAL_JOGADORES <- 0<br>TOTAL_ALTURA <- 0<br>TOTAL_PESO_MAIS_80 <- 0"]
    B --> C{PARA TIME DE 1 ATÉ 5}
    
    C -- Loop --> D["SOMA_IDADE_TIME <- 0"]
    D --> E{PARA JOGADOR DE 1 ATÉ 11}
    
    E -- Loop --> F[/"LEIA IDADE, PESO, ALTURA"/]
    F --> G["SOMA_IDADE_TIME <- SOMA_IDADE_TIME + IDADE<br>TOTAL_ALTURA <- TOTAL_ALTURA + ALTURA<br>TOTAL_JOGADORES <- TOTAL_JOGADORES + 1"]
    G --> H{IDADE < 18}
    H -- Sim --> I["TOTAL_MENORES_18 <- TOTAL_MENORES_18 + 1"]
    H -- Não --> J{PESO > 80}
    I --> J
    J -- Sim --> K["TOTAL_PESO_MAIS_80 <- TOTAL_PESO_MAIS_80 + 1"]
    J -- Não --> L((Volta))
    K --> L
    L --> E
    
    E -- Fim do Loop Interno --> M["MEDIA_IDADE_TIME <- SOMA_IDADE_TIME / 11"]
    M --> N[/"ESCREVA MEDIA_IDADE_TIME"/]
    N --> C
    
    C -- Fim do Loop Principal --> O["MEDIA_ALTURA_CAMPEONATO <- TOTAL_ALTURA / TOTAL_JOGADORES<br>PORCENTAGEM_PESO <- (TOTAL_PESO_MAIS_80 / TOTAL_JOGADORES) * 100"]
    O --> P[/"ESCREVA RESULTADOS FINAIS"/]
    P --> Z([Fim])
```

---

### 6. Verificação de Número Primo

```mermaid
graph TD
    A([Início]) --> B[/"LEIA NUMERO"/]
    B --> C{NUMERO <= 1}
    
    C -- Sim --> D[/"ESCREVA 'NUMERO INVALIDO'"/]
    D --> Z([Fim])
    
    C -- Não --> E["TOTAL_DIVISORES <- 0"]
    E --> F{PARA DIVISOR DE 1 ATÉ NUMERO}
    
    F -- Loop --> G{NUMERO MOD DIVISOR = 0}
    G -- Sim --> H["TOTAL_DIVISORES <- TOTAL_DIVISORES + 1"]
    G -- Não --> I((Volta))
    H --> I
    I --> F
    
    F -- Fim do Loop --> J{TOTAL_DIVISORES = 2}
    
    J -- Sim --> K[/"ESCREVA 'O NUMERO E PRIMO'"/]
    J -- Não --> L[/"ESCREVA 'O NUMERO NAO E PRIMO'"/]
    
    K --> Z
    L --> Z
```

---

### 7. Área do Triângulo com Validação

```mermaid
graph TD
    A([Início]) --> B{REPITA}
    B --> C[/"LEIA BASE"/]
    C --> D{BASE <= 0}
    D -- Sim --> E[/"ESCREVA 'MEDIDA INVALIDA'"/]
    D -- Não --> F((Continua))
    E --> F
    F --> G{ATÉ BASE > 0}
    G -- Falso --> B
    
    G -- Verdadeiro --> H{REPITA}
    H --> I[/"LEIA ALTURA"/]
    I --> J{ALTURA <= 0}
    J -- Sim --> K[/"ESCREVA 'MEDIDA INVALIDA'"/]
    J -- Não --> L((Continua))
    K --> L
    L --> M{ATÉ ALTURA > 0}
    M -- Falso --> H
    
    M -- Verdadeiro --> N["AREA <- (BASE * ALTURA) / 2"]
    N --> O[/"ESCREVA AREA"/]
    O --> Z([Fim])
```

---

### 8. Quadrado, Cubo e Raiz

```mermaid
graph TD
    A([Início]) --> B{REPITA}
    B --> C[/"LEIA VALOR"/]
    C --> D{VALOR > 0}
    
    D -- Sim --> E["QUADRADO <- VALOR * VALOR<br>CUBO <- VALOR * VALOR * VALOR<br>RAIZ <- RAIZ_QUADRADA(VALOR)"]
    E --> F[/"ESCREVA VALOR, QUADRADO, CUBO, RAIZ"/]
    F --> G{ATÉ VALOR <= 0}
    
    D -- Não --> G
    
    G -- Falso --> B
    G -- Verdadeiro --> Z([Fim])
```

---

### 9. Soma de Pares (M e N)

```mermaid
graph TD
    A([Início]) --> B{REPITA}
    B --> C[/"LEIA M, N"/]
    C --> D{M < N}
    
    D -- Sim --> E["SOMA <- 0"]
    E --> F{PARA I DE M ATÉ N}
    
    F -- Loop --> G["SOMA <- SOMA + I"]
    G --> F
    
    F -- Fim do Loop --> H[/"ESCREVA SOMA"/]
    H --> I{ATÉ M >= N}
    
    D -- Não --> I
    
    I -- Falso --> B
    I -- Verdadeiro --> Z([Fim])
```