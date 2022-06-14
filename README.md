```
Table aluno {
  id integer [pk, increment]
  name varchar
  cpf varchar [unique]
  email varchar
  phone varchar [null]
  birthday timestamp
  created_at timestamp
  updated_at timestamp [null]
}

Table professor {
  id integer [pk, increment]
  idDepartamento integer [ref: > departamento.id]
  idCargo integer [ref: > cargo.id]
  name varchar
  cpf varchar [unique]
  email varchar
  phone varchar
  birthday timestamp
  admission timestamp
  created_at timestamp
  updated_at timestamp [null]
}

Table funcionario {
  id integer [pk, increment]
  idDepartamento integer [ref: > departamento.id]
  name varchar
  cpf varchar [unique]
  email varchar
  phone varchar
  admission timestamp
  created_at timestamp
  updated_at timestamp [null]
}

Table especialidade {
  id integer [pk, increment]
  name varchar
  created_at timestamp
  updated_at timestamp [null]
}

Table cargo {
  id integer [pk, increment]
  name varchar
  created_at timestamp
  updated_at timestamp [null]
}

Table curso {
  id integer [pk, increment]
  idDepartamento varbinary [ref: > departamento.id]
  name varchar
  created_at timestamp
  updated_at timestamp [null]
}

Table nota {
  id integer [pk, increment]
  value numeric
}

Table departamento {
  id integer [pk, increment]
  name varchar
  created_at timestamp
  updated_at timestamp [null]
}

Table historico_aluno {
  id integer [pk, increment]
  created_at timestamp
}

Table professor_especialidade {
  idProfessor integer [ref: > professor.id]
  idEspecialidade integer [ref: > especialidade.id]
}

Table aluno_curso_nota {
  id integer [pk, increment]
  idAluno integer [ref: > aluno.id]
  idCurso integer [ref: > curso.id]
  idNota integer [ref: > nota.id]
}

Table historico_aluno_aluno_curso_nota {
  idHistorico integer [ref: > historico_aluno.id]
  aluno_curso_nota integer [ref: > aluno_curso_nota.id]
}
```
