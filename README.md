# Persistência de Aluno com MongoDB simulado

Solução da atividade baseada em https://github.com/TQSA6/semana-11-aula.

## Executar

Requer Python 3.9 ou superior.

```bash
python -m pip install -r requirements.txt
python -m unittest -v testes
```

Não é necessário instalar ou iniciar um servidor MongoDB.

## Métodos implementados

- `AlunoClass.salvar(self, conexao, colecao)`: monta um documento com nome, sobrenome e nota, chama `insert_one` na coleção recebida e retorna `acknowledged`. Usa um novo dicionário para que a inclusão de `_id` pelo driver não altere os atributos do aluno.
- `alunoTest.test_salvarAluno(self)`: salva o aluno e verifica o retorno, a quantidade de documentos, os dados persistidos e a preservação dos atributos do objeto.

O `mongomock.patch` do exemplo substitui `pymongo.MongoClient` por um banco em memória durante o `setUp`. Cada teste recebe uma conexão simulada nova. O teste original de turma foi preservado.

## Publicar no GitHub

Crie um repositório chamado `semana-11-aula-solucao` na sua conta e envie os arquivos deste projeto. Depois, entregue a URL do repositório.

