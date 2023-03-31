1. _agruparContasESaldos(lancamentos)_

```
- Tipo de parâmetro de entrada: array. Lista com todos os lançamentos de todos os cpfs.

- Tipo de retorno: object. Um objeto onde as chaves são os cpfs e os valores são os 
respectivos saldos.

- Descrição: com base na lista de todos os lançamentos, usa um laço "for" para separar os CPFs
e associar cada um deles ao seu saldo. {'cpf1': saldo, 'cpf2': saldo, ..., 'cpf': saldo}
```

2. _calcularPrimeiroDigitoDoCPF(cpf)_

```
- Tipo de parâmetro de entrada: string. O cpf informado.
- Tipos de retorno: number. O primeiro dígito verificador do cpf, com base nos dígitos anteriores. 
```

3. _calcularSegundoDigitoDoCPF(cpf)_

```
- Tipo de parâmetro de entrada: string. O cpf informado.
- Tipos de retorno: number. O segundo dígito verificador do cpf, com base nos dígitos anteriores. 
```

4. _ordenarMaioresMedias(mediasPorConta)_

```
- Tipo de parâmetro de entrada: object. Um objeto contendo os CPFs como chaves e as respectivas
médias como valores.

- Tipo de retorno: array. Uma lista de objetos, ordenada da maior para a menor média, onde cada
item é um objeto no seguinte formato: [{cpf: 'cpf1', valor: media}, {cpf: 'cpf2', valor: media}, ... ,{cpf: 'cpf', valor: media}]

- Descrição: partindo do objeto contendo as medias por conta, esta função gera duas listas:
uma contendo as contas (CPFs) e outra contendo as medias.

Com essas duas listas, faz uso de uma lista auxiliar para gerar uma terceira lista, composta
por pares [cpf, média], ordenados da maior para a menor média.

Por fim, converte essa terceira lista em uma lista final, composta de objetos no formato
{cpf: 'cpf', valor: 'media'}, ordenados da maior para a menor média.
```

5. _ordenarMaioresSaldos(contasESaldos)_

```
- Tipo de parâmetro de entrada: object. Um objeto no formato {'cpf1': saldo, 'cpf2': saldo, ..., 'cpf': saldo}

- Tipo de retorno: array. Uma lista contendo o saldo de cada CPF, ordenados do maior saldo
para o menor saldo.
Exemplo: [{cpf: 'cpf1', valor: saldo}, {cpf: 'cpf2', valor: saldo}, ... ,{cpf: 'cpf', valor: saldo}]

- Descrição: recebe como parâmetro um objeto que é gerado pela função _agruparContasESaldos_
(também descrita nesta documentação). Transforma esse objeto em uma lista de listas, onde cada
lista menor é composta de dois elementos: o CPF e o saldo correspondente.

Exemplo: [['cpf1', saldo], ['cpf2', saldo], ... ,['cpf', saldo]]

Esta lista então é ordenada, do maior para o menor saldo, e depois transformada novamente um objeto.
```

6. _recuperarMaioresLancamentos(lancamentos)_

```
- Tipo de parâmetro de entrada: array. Uma lista com todos os lançamentos de todos os CPF's.

Exemplo: [{cpf: 'cpf1', valor: valor_1}, {cpf: 'cpf2', valor: valor_2}, ... ,{cpf: 'cpf', valor: valor}]

- Tipo de retorno: object. Um objeto onde cada chave é um CPF e cada valor é o maior lancamento
correspondente para o respectivo CPF.

Exemplo: {'cpf1': maior_lancamento-cpf1, 'cpf2': maior_lancamento-cpf2, ..., 'cpf': maior_lancamento-cpf}

- Descrição: com base na lista de todos os lançamentos de todos os CPFs, usa um laço "for" para gerar
um objeto contendo somente o maior lançamento feito por cada CPF.
```

7. _recuperarMediaPorConta(contasESaldos, quantidadeLancamentosPorConta)_

```
- Tipo de parâmetro de entrada: object, object. "contasESaldos" é um objeto contendo cada CPF
associado ao respectivo saldo. "quantidadeLancamentosPorConta" é um objeto contendo cada CPF
associado a respectiva quantidade de lançamentos feitas. 

- Tipo de retorno: object. Um objeto contendo os CPFs como chaves e as respectivas médias 
dos lançamentos feitos por cada um.
Exemplo: {'cpf1': media-1, 'cpf2': media-2, ..., 'cpf': media} 

- Descrição: a partir de contasESaldos, gera uma lista com todas as contas. Usa um laço "for"
para iterar por cima da lista de contas. Usando o CPF como chave, pega o valor do saldo e divide
pelo número de lançamentos para calcular a media. Agora com a media, gera um novo objeto, com o 
CPF como chave e a média como valor.
```

8. _recuperarMenoresLancamentos(lancamentos)_

```
- Tipo de parâmetro de entrada: array. Uma lista com todos os lançamentos de todos os CPF's.

Exemplo: [{cpf: 'cpf1', valor: valor_1}, {cpf: 'cpf2', valor: valor_2}, ... ,{cpf: 'cpf', valor: valor}]

- Tipo de retorno: object. Um objeto onde cada chave é um CPF e cada valor é o menor lancamento
correspondente para o respectivo CPF.

Exemplo: {'cpf1': menor_lancamento-cpf1, 'cpf2': menor_lancamento-cpf2, ..., 'cpf': menor_lancamento-cpf}

- Descrição: com base na lista de todos os lançamentos de todos os CPFs, usa um laço "for" para gerar
um objeto contendo somente o menor lançamento feito por cada CPF.
```

9. _recuperarQuantidadeLancamentosPorConta(lancamentos)_

```
- Tipo de parâmetro de entrada: array. Uma lista com todos os lançamentos já feitos. 

- Tipo de retorno: object. Um objeto contendo os CPFs como chaves e as respectivas quantidades 
de lançamentos feitos por cada um.
Exemplo: {'cpf1': qtd-de-lancamentos-1, 'cpf2': qtd-de-lancamentos-2, ..., 'cpf': qtd-de-lancamentos} 

- Descrição: recebe como parâmetro uma lista com todos os lançamentos já feitos. Usando um loop em
"for", gera um único objeto onde cada chave é um CPF e cada valor correspondente é o número de
lançamentos feitos por aquele CPF.
```

10. _separarSaldoPorConta(contasESaldos)_

```
- Tipo de parâmetro de entrada: object. Um objeto no formato {'cpf1': saldo, 'cpf2': saldo, ..., 'cpf': saldo} 

- Tipo de retorno: array. Uma lista de objetos no formato
[{cpf: 'cpf1', valor: saldo}, {cpf: 'cpf2', valor: saldo}, ... ,{cpf: 'cpf', valor: saldo}]

- Descrição: recebe como parâmetro um objeto que é gerado pela função _agruparContasESaldos_
(também descrita nesta documentação). Formata objeto recebido gerando um array a partir dele.
Este array, por sua vez, é composto de vários objetos onde cada um deles representa uma 
conta e um lançamento.
```

11. _validarCPF(cpf)_

- Tipo de parâmetro de entrada: string. O cpf informado.

- Tipos de retorno: string || null. Retorna uma mensagem de erro se o CPF for inválido, ou null
se estiver tudo certo.

- Descrição: verifica se o CPF informado é válido, com base em 3 regras: a) O CPF deve ser um
número, não contendo traços nem pontos. b) O CPF deve ter 11 dígitos. c) O CPF deve ter os dígitos
verificadores válidos.  

12. _validarValor(cpf)_

```
- Tipo de parâmetro de entrada: number. O valor informado.

- Tipos de retorno: string || null. Retorna uma mensagem de erro se o valor for inválido, ou null
se estiver tudo certo.

- Descrição: verifica se o valor informado é válido, com base em duas regras: a) Um número deve
ser informado. b) O numero deve estar entre -2000 e 15000.
```

13. _verificarDoisUltimosDigitosDoCPF(cpf)_

```
- Tipo de parâmetro de entrada: string. O cpf informado.

- Tipos de retorno: boolean. Retorna "true" se os dois dígitos verificadores estiverem corretos,
e "false" caso não estejam. 

- Descrição: Com base nos primeiros dígitos do cpf, esta função calcula aqueles que
deveriam ser seus dois dígitos verificadores. Feito esse cálculo, ela compara com os dígitos que
foram de fato informados no cpf.  
```
