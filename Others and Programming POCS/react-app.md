## Criar App React


Inicie um novo projeto React usando o comando npx create-react-app nome-do-projeto.

No arquivo App.js, adicione os campos de entrada para a data início, data fim, nome do operador da transação e o botão de pesquisar. Usar elementos HTML como input e button para isso.

```javascript
import React, { useState } from 'react';

function App() {
  const [startDate, setStartDate] = useState('');
  const [endDate, setEndDate] = useState('');
  const [operator, setOperator] = useState('');

  const handleSearch = () => {
    // Faça a pesquisa aqui usando os valores de startDate, endDate e operator
  };

  return (
    <div>
      <label htmlFor="start-date">Data início:</label>
      <input type="date" id="start-date" value={startDate} onChange={e => setStartDate(e.target.value)} />
      <br />
      <label htmlFor="end-date">Data fim:</label>
      <input type="date" id="end-date" value={endDate} onChange={e => setEndDate(e.target.value)} />
      <br />
      <label htmlFor="operator">Nome do operador:</label>
      <input type="text" id="operator" value={operator} onChange={e => setOperator(e.target.value)} />
      <br />
      <button onClick={handleSearch}>Pesquisar</button>
    </div>
  );
}

export default App;
```

Criar uma tabela HTML para exibir os resultados da pesquisa. Usar elementos HTML como table, thead, tbody e tr para isso.

```javascript
import React from 'react';

function App() {
  // ...

  return (
    <div>
      {/* ... */}
      <table>
        <thead>
          <tr>
            <th>Data da transação</th>
            <th>Dinheiro</th>
            <th>Tipo de transferência</th>
            <th>Nome do operador</th>
          </tr>
        </thead>
        <tbody>
          {/* Adicione as linhas da tabela aqui */}
        </tbody>
      </table>
      {/* Exiba o saldo total e o saldo em um determinado período de tempo aqui */}
    </div>
  );
}

export default App;
```
No método handleSearch, fazer a chamada à API para obter os dados da pesquisa e atualizar o estado da aplicação.
