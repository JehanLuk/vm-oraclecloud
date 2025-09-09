# vm-oraclecloud
Desafio de projeto da DIO: criação de máquina virtual com documentação

> Nota: Estou utilizando a versão `Always Free` do Oracle Cloud, alguns recursos da versão paga podem não estar disponíveis na minha revisão.

---

## Bloco de `Build` com Serviços
![Bloco de Build com Serviços](images/build.png)

Existem alguns serviços presentes no Oracle Cloud, neste seguimento vou abordar a `Criação de Instância de Máquina Virtual` e uma estimativa de tempo para a criação de cada unidade, ao clicar no link você será redirecionado para a aba `Compute`

---

## Basic Information (Informação Básica)

![Aba de Informações Básicas](images/basicInfo.png)

Podemos observar algumas caixas de texto e de seleção, como por exemplo:

- **Name (Nome)**: Nome da instância que você está criando. Ex: `instance-20250909-1918`.
- **Compartment (Compartimento)**: O compartimento onde a instância será criada
> Por padrão o OCID (Oracle Cloud ID) utiliza uma versão simplificada do `tenancy` (conta da Oracle Cloud) e identifica um `root compartment` (Compartimento Raíz), contas pessoais costumam utilizar apenas um compartimento, é muito comum a criação de vários compartimentos em ambiente empresarial devido a separação de recursos do projeto.

### **Placement (Posicionamento)**

- **Availability Domain (Domínio de Disponibilidade)**

Define em qual domínio de disponibilidade (data center lógico dentro da região) a instância será provisionada. <br>Ex no print: `BDXQ:SA-SAOPAULO-1-AD-1` (Significa que minha instância será criada no data center da Oracle em São Paulo, sendo um serviço de **IaaS**). 

### Advanced Options (Opções Avançadas) - **Opcional**

- **Capacity Type (Tipos de Capacidade)**

1. On-demand capacity (Capacidade sob demanda)

É o padrão. A Oracle reserva os recursos de CPU/memória para você assim que criar a instância.<br>
**Vantagem**: garante que a VM sempre subirá quando você precisar.<br>
**Desvantagem**: custo mais alto.

2. Preemptible capacity (Capacidade preemptiva)

Instância criada com capacidade temporária que pode ser interrompida pela Oracle a qualquer momento, caso os recursos forem necessários em outro lugar.<br>
**Vantagem**: custo muito baixo, bom para testes ou processamento que pode ser interrompido.<br>
**Desvantagem**: instâncias podem ser encerradas a qualquer momento.<br>

3. Capacity reservations (reserva de capacidade)

Você pode reservar antecipadamente recursos de CPU/memória numa região.
Útil em ambientes críticos onde você precisa garantir que sempre haverá recursos disponíveis.<br>
**Vantagem**: garante recursos disponíveis para ambientes críticos.<br>
**Desvantagem**: geralmente caro e voltado para empresas grandes.

4. Dedicated Host (Host dedicado)

Você aluga um servidor físico inteiro só para você, em vez de compartilhar com outros clientes (que é o padrão da nuvem).<br>
**Vantagem**: servidor físico exclusivo só para você, sem compartilhar recursos.<br>
**Desvantagem**: muito caro; não está incluso no Always Free.

5. Cluster Network (Compute Cluster)

Conjunto de várias instâncias Bare Metal ou instâncias com RDMA (Remote Direct Memory Access) interconectadas.<br>
**Vantagem**: alta performance e baixa latência para aplicações que exigem RDMA ou múltiplas VMs interconectadas.<br>
**Desvantagem**: complexo e caro; não está incluso no Always Free.

> somente os **recursos específicos** de VM do tipo `Always Free` estão isentos de cobrança.