# Configurando Armazenamento na Azure

##  Entendendo o Desafio
Este repositório contém meu resumo do módulo sobre **Armazenamento no Azure**, desenvolvido durante o laboratório da DIO.  
O objetivo foi compreender os principais conceitos de **contas de armazenamento, redundância, serviços, camadas de acesso e migração de dados**, aplicando na prática o que foi estudado.

---

### 🔑 Contas de Armazenamento
- O nome da conta deve ser **globalmente exclusivo**.  
- Fornece acesso via Internet em todo o mundo.  
- Determina os **serviços de armazenamento** disponíveis.  
- Pode ser comparado com uma “caixa” que organiza os dados em **blobs, filas, mensagens, tabelas, etc.**

---

### 🌀 Redundância de Armazenamento

| Configuração | Implantação | Durabilidade |
|--------------|-------------|--------------|
| **LRS (Local Redundant Storage)** | Datacenter único na região primária | 11 noves |
| **ZRS (Zone Redundant Storage)** | 3 zonas de disponibilidade na região primária | 12 noves |
| **GRS (Geo Redundant Storage)** | Datacenter único no primário + réplica em região secundária | 16 noves |
| **GZRS (Geo Zone Redundant Storage)** | 3 zonas na região primária + 1 datacenter em região secundária | 16 noves |

📌 **Principais para prova:** LRS e ZRS.   
Quanto mais “noves” (ex.: 99,99…), maior a disponibilidade (SLA).

---

### 📦 Serviços de Armazenamento
- **Blob do Azure** → Armazena dados massivos não estruturados (texto, binário).  
- **Disco do Azure** → Discos para máquinas virtuais e apps.  
- **Fila do Azure** → Armazenamento de mensagens (até 64 KB cada).  
- **Arquivos (Azure Files)** → Compartilhamento de arquivos SMB.  
- **Tabelas do Azure** → Dados estruturados não relacionais (chave/atributo).  

---

### 🌍 Pontos de Extremidades Públicos

| Serviço | URL de acesso |
|---------|---------------|
| Blobs | `https://<nome-da-conta-de-armazenamento>.blob.core.windows.net` |
| Data Lake Gen2 | `https://<nome-da-conta-de-armazenamento>.dfs.core.windows.net` |
| Arquivos | `https://<nome-da-conta-de-armazenamento>.file.core.windows.net` |
| Filas | `https://<nome-da-conta-de-armazenamento>.queue.core.windows.net` |
| Tabelas | `https://<nome-da-conta-de-armazenamento>.table.core.windows.net` |

---

### 🏷️ Camadas de Acesso
- **Frequente** → dados acessados constantemente.  
- **Esporádico** → dados pouco acessados (mín. 30 dias).  
- **Frio** → dados raramente acessados (mín. 90 dias).  
- **Arquivo Morto** → dados de longo prazo (mín. 180 dias, latência maior).  

---

### 🚚 Migrações para o Azure
- **Plataforma de Migração Unificada** → mover workloads on-premises para nuvem.  
- **Azure Data Box** → envio físico de até **80 TB** em caixas protegidas.  
  - Ideal para volumes **>40TB**, locais remotos ou sem conectividade.  

---

### ⚙️ Opções de Gerenciamento de Arquivos
- **AzCopy** → ferramenta CLI, copia/sincroniza blobs/arquivos.  
- **Gerenciador de Armazenamento do Azure** → GUI multiplataforma (Win, Mac, Linux).  
- **Sincronização de Arquivos do Azure** → sincronização **bidirecional**, mantém arquivos usados no local e libera espaço (similar ao OneDrive).  

---

## 🚀 Como Executar o Desafio
1. Criar conta no GitHub.  
2. Criar repositório público (ex.: `resumo-armazenamento-azure`).  
3. Editar o arquivo `README.md` adicionando este resumo.  
4. Realizar commit e compartilhar o link no portal da DIO.  

---

## 📎 Recursos Úteis
- [Documentação oficial do Azure Storage](https://learn.microsoft.com/azure/storage)  
- [AzCopy - Microsoft Docs](https://learn.microsoft.com/azure/storage/common/storage-use-azcopy-v10)  
- [Azure Data Box](https://learn.microsoft.com/azure/databox/data-box-overview)  

---