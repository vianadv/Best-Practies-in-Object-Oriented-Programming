Se o seu tipo primitivo possuir regras, validações ou comportamentos, é recomendado envolvê-lo (criar uma classe para ele). Um tipo primitivo como `String` pode representar um e-mail, um CPF ou um nome. Uma classe `Email` ou `CPF` torna claro o propósito do dado, melhorando a legibilidade do código.

Uma classe `Aluno` possui atributos como idade, e-mail e CPF; porém, não é responsabilidade do `Aluno` validar esses atributos. Logo, devemos encapsular esses dados em classes próprias.

Portanto: se um dado possui regras, ele merece uma classe.

[[00obj]]