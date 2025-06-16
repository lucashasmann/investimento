📱 Descrição do Projeto


Nome sugerido: Simulador de Investimentos - Paciência Financeira
🎯 Objetivo
Permitir que o usuário veja quanto dinheiro ele acumulará ao investir um valor fixo mensal, por um número fixo de meses, com uma taxa de juros mensal.
O app mostrará:

O montante sem juros (soma dos depósitos);

O montante com juros compostos (crescimento real do investimento).

🛠️ Tecnologias Utilizadas
Tecnologia	Função principal
Dart	Lógica da aplicação
Flutter	Interface gráfica do app
Firebase	Armazenamento de simulações anteriores (opcional)
Firestore	Base de dados em nuvem
Firebase CLI	Testes locais / deploy web ou mobile

🧮 Fórmula e Lógica com Repetição
Usaremos um laço de repetição (for loop) para simular o crescimento do capital com aportes mensais e juros compostos, como em uma planilha de Excel.

Fórmulas:
Sem juros:
totalSemJuros = valorMensal × meses

Com juros compostos e aportes mensais:

dart
Copiar
Editar
double montante = 0;
for (int i = 0; i < meses; i++) {
  montante = (montante + valorMensal) * (1 + taxaJuros);
}
📲 Entradas do Usuário
Valor mensal a ser investido;

Número de meses;

Taxa de juros mensal (%).

📊 Saídas do App
Total investido (sem juros);

Total com juros compostos;

(Opcional) Mostrar evolução mês a mês.

⚙️ Como executar o projeto (Flutter + Firebase)
Se você já seguiu o passo a passo anterior para configurar Firebase no Flutter, pode reaproveitar a base e adicionar essa nova funcionalidade como outra aba/página no app.

🚧 Exemplo de lógica completa em Dart:
dart
Copiar
Editar
double calcularSemJuros(double valorMensal, int meses) {
  return valorMensal * meses;
}

double calcularComJuros(double valorMensal, double taxaJuros, int meses) {
  double montante = 0;
  for (int i = 0; i < meses; i++) {
    montante = (montante + valorMensal) * (1 + taxaJuros);
  }
  return montante;
}
🧾 (Opcional) Salvar simulações no Firestore
dart
Copiar
Editar
FirebaseFirestore.instance.collection('investimentos').add({
  'mensal': valorMensal,
  'meses': meses,
  'taxa': taxaJuros,
  'total_sem_juros': totalSemJuros,
  'total_com_juros': totalComJuros,
  'data': Timestamp.now(),
});
▶️ Executar o app
bash
Copiar
Editar
flutter run


![investimento](https://github.com/user-attachments/assets/3f874495-784f-46e4-ad9f-a7abf77849ad)

