# nicoleeagathaebia
trabalho das super divas lindas

// index.js
const express = require('express');
const app = express();

// Middleware para ler o body das requisições em formato JSON
app.use(express.json());

// Rota de exemplo que recebe um body
app.post('/api/dados', (req, res) => {
  const body = req.body;

  // Verifica se o body foi enviado
  if (!body) {
    return res.status(400).json({ message: 'Body não encontrado' });
  }

  // Retorna a resposta com o corpo da requisição
  res.status(200).json({
    message: 'Dados recebidos com sucesso',
    dados: body,
  });
});

// Inicia o servidor
const PORT = 3000;
app.listen(PORT, () => {
  console.log(`Servidor rodando na porta ${PORT}`);
});
