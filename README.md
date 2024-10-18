Resumo dos laboratórios do curso de certificação para o AZ-900 da DIO.

Nesse primeiro momento tivemos um overview dos serviçoes da Microsoft Azure.

> Modelos de nuvem
Nuvem Privada - On Promises, a responsabilidade é inteira que quem tem o sistema de cluster.
Nuvem Pública - Responsabilidade compartilhada, hardware é responsábilidade da Empresa da nuvem e a empresa contratante fica responséval por escalar e escolher os serviços de acordo com sua necessidade. Tem rapidez para criar e descriar aplicativos.
Nuvem Híbrida - Melhor dos dois mundos, tem parte na empresa contratante e parte na empresa de nuvem. Escolho por requisite de preço, cabe a eu como empresa escolher o que é melhor para cada serviço, manter comigo ou com a nuvem.
Modelo Multicloud - Tem mais de uma empresa de nuvem.

> Capex e Opex
Capex é despesa de capital, ou seja, tenho um valor inicial para gastar e com o tempo o custo vai se estabilizando para baixo.
Opex é despesa operacional, é gasto conforme o uso, seja vertical, horizontal e tempo. Modelo baseado em consume, quanto mais usa ou tempo ligado, mais paga.

> Mapas Mentais AZ-900
https://art-verse.com/2021/01/16/microsoft-azure-900-fundamentals-cloud-computing-cheat-sheet-1-free-download/

---

> * Alta disponibilidade - A microsoft, para cada, produto darante uma porcentagem mínima para manter o produto disponível. O que significa que o produto pode sair fora do ar e que está previsto em contrato. Se o tempo for maior que o previsto, a microsoft ressarci devolvento o tempo excedente em voucher.  
> * Escalabilidade foca na capacidade de aumentar ou diminuir recursos, seja manual ou automaticamente.  
> * Elasticidade garante que o sistema aumente ou diminua automaticamente conforme a demanda muda, ajustando os recursos em tempo real.  
> * Confiabilidade - Resiliência, se por exemplo, em alguma determinada região cair, a microsoft vai poder garantia porque em outro lugar vai estar funcionando.  
> * Previsibilidade - Confiança para moder mudar, avançar para a numve do Azure.  
> * Segurança - A implementação não é de responsabilidade da Microsoft. Mas ela tem serviços que consigam dar a segurança para a empresa.
> * Governança - Como gerir os recursos. Fazer auditoria, SLA.
> * Gerenciabilidade - Pode monitorar e editar de várias formas, como via navegador, terminal, arquivo e api.  
> 
> \* Importante lembrar que SLA é o tempo que o serviço está disponível.

---

## Tipo de serviço de Nuvem
Esse é um Contexto genérico de nuvem.

IAAS - Infraestrutura como serviço. Teremos mais acesso, mas interatividade. É mais personalizável. A responsabilidade do cliente é maior.  
PAAS - Plataforma como serviço. Já não se importa mais com o sistema operacional.
SAAS - Software como serviço. Tem acesso direto aos aplicativos. Menos configurações possíveis.
Ex.: Office 365.

## Redundância de Armazenamento
Aqui está uma explicação detalhada sobre os tipos de redundância de armazenamento no Azure e o número de cópias envolvidas:

### 1. **LRS (Locally Redundant Storage)**
- **Cópias**: Mantém 3 cópias dos dados.
- **Localização**: Todas as cópias estão dentro de um único datacenter (ou seja, dentro de uma mesma região).
- **Risco**: Protege contra falhas locais de hardware, mas não contra falhas ou desastres na região inteira (ex.: terremoto, incêndio).
- **Uso comum**: Cenários de menor custo onde a alta disponibilidade regional não é crítica.

### 2. **ZRS (Zone-Redundant Storage)**
- **Cópias**: Mantém 3 cópias dos dados.
- **Localização**: Distribui as cópias entre diferentes zonas de disponibilidade dentro da mesma região. Cada zona é um conjunto de datacenters fisicamente separados.
- **Risco**: Protege contra falhas em zonas específicas, como queda de energia em um datacenter, pois as cópias estão em locais diferentes dentro da mesma região.
- **Uso comum**: Aplicações que requerem alta disponibilidade dentro de uma única região, mas não necessariamente recuperação de desastres em nível global.

### 3. **GRS (Geo-Redundant Storage)**
- **Cópias**: Mantém 6 cópias dos dados (3 em uma região primária + 3 em uma região secundária).
- **Localização**: As 3 cópias primárias estão em um único datacenter (como LRS), e as 3 cópias secundárias estão em uma região geograficamente distante (em um datacenter de outra região).
- **Risco**: Protege contra falhas regionais completas, como desastres naturais. No entanto, o acesso à cópia secundária só é permitido no caso de um failover.
- **Uso comum**: Cenários onde a recuperação de desastres em nível global é importante.

### 4. **GZRS (Geo-Zone-Redundant Storage)**
- **Cópias**: Mantém 6 cópias dos dados (3 cópias distribuídas entre diferentes zonas de uma região primária + 3 cópias em uma região secundária).
- **Localização**: Combina o ZRS (3 cópias em diferentes zonas de uma região) com a replicação geográfica (3 cópias em uma região secundária).
- **Risco**: Protege tanto contra falhas de zona quanto contra desastres regionais. Em caso de falha regional, as cópias secundárias podem ser ativadas via failover.
- **Uso comum**: Para cargas de trabalho críticas que exigem a mais alta disponibilidade e recuperação de desastres.

### Resumo:
- **LRS**: 3 cópias em um datacenter dentro da mesma região.
- **ZRS**: 3 cópias em diferentes zonas de uma única região.
- **GRS**: 6 cópias (3 em uma região primária e 3 em uma secundária geograficamente distante).
- **GZRS**: 6 cópias (3 entre diferentes zonas de uma região primária + 3 em uma região secundária).

Isso ajuda a garantir a alta disponibilidade e a recuperação de desastres de acordo com as necessidades da sua aplicação.

