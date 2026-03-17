# Sistema de Reserva de Quadras - Condomínio
## Histórias de Usuário

### 1. Reserva de Espaço Esportivo
**Como** morador,  
**Quero** conseguir reservar uma quadra,  
**Para** garantir meu horário de lazer sem conflitos com outros vizinhos.

**Critérios de Aceitação:**
* **Cenário: Realizar reserva com sucesso**
    * **Dado que** eu estou na tela de "Nova Reserva";
    * **E** selecionei o "Campo de Fut7";
    * **E** escolhi uma data e horário disponíveis;
    * **Quando** eu clicar no botão "Confirmar Reserva";
    * **Então** o sistema deve salvar o agendamento no meu perfil;
    * **E** deve exibir uma mensagem de confirmação: "Reserva realizada com sucesso!".

---

### 2. Validação de Conflitos e Disponibilidade
**Como** morador,  
**Quero** visualizar apenas horários disponíveis,  
**Para** não tentar reservar um espaço que já está sendo utilizado por outro condômino.

**Critérios de Aceitação:**
* **Cenário: Tentar reservar horário já ocupado**
    * **Dado que** a "Quadra de Tênis" já possui uma reserva para às 10:00 do dia atual;
    * **E** eu tento selecionar esse mesmo horário na grade;
    * **Quando** o sistema carregar as opções de agendamento;
    * **Então** o horário das 10:00 deve aparecer com o status "Ocupado" ou desabilitado;
    * **E** o sistema deve impedir qualquer clique ou submissão para este período específico.

---

### 3. Gestão de Desistência e Cancelamento
**Como** morador,  
**Quero** conseguir cancelar uma reserva antecipadamente,  
**Para** liberar o espaço para outros moradores caso eu não possa comparecer.

**Critérios de Aceitação:**
* **Cenário: Cancelamento dentro do prazo regulamentar**
    * **Dado que** eu possuo uma reserva ativa para a "Quadra de Basquete";
    * **E** o horário de início da reserva é superior a 2 horas (prazo padrão) a partir do momento atual;
    * **Quando** eu selecionar a opção "Cancelar Reserva" no meu painel;
    * **Então** o sistema deve remover o vínculo da reserva com o meu usuário;
    * **E** tornar o horário imediatamente "Disponível" para todo o condomínio.

---

### 4. Regras de Uso e Rotatividade
**Como** morador,  
**Quero** que o sistema respeite o tempo limite de cada tipo de quadra,  
**Para** que a divisão de tempo entre os condôminos seja justa e organizada.

**Critérios de Aceitação:**
* **Cenário: Verificação de tempo máximo por categoria**
    * **Dado que** o regimento define 1h para Tênis e 1h30 para Fut7;
    * **Quando** eu selecionar a "Quadra de Tênis" no formulário;
    * **Então** o sistema deve limitar a seleção de horário a blocos de 60 minutos;
    * **E** ao trocar para "Campo de Fut7", o intervalo deve ser ajustado automaticamente para 90 minutos.

---

### 5. Restrição por Inadimplência
**Como** morador,  
**Quero** ter acesso ao sistema de reservas apenas se estiver em dia com as taxas condominiais,  
**Para** cumprir com as normas do regimento interno do condomínio.

**Critérios de Aceitação:**
* **Cenário: Bloqueio de acesso por pendência financeira**
    * **Dado que** meu cadastro possui o status de "Inadimplente" no banco de dados;
    * **Quando** eu tentar acessar o módulo de "Reservas";
    * **Então** o sistema deve bloquear a visualização do calendário;
    * **E** exibir a mensagem: "Reservas suspensas. Por favor, regularize sua situação com a administração para liberar o acesso.".
