## Criando maquina Virtual no Portal Azure



# 🚀 Criando uma Máquina Virtual no Azure com Windows Server

Este guia passo a passo mostra como criar uma máquina virtual (VM) no Azure, configurar o acesso remoto via RDP, instalar o servidor Web IIS e visualizar a página de boas-vindas do IIS.

---

## 🛠️ Criar uma Máquina Virtual

### 1. Acesse Máquinas Virtuais no Portal Azure

- Pesquise por **Máquinas Virtuais** no portal Azure.
- Clique em **Criar** > **Máquina virtual do Azure**.

![Detalhes da Instância](https://via.placeholder.com/800x400?text=Detalhes+da+Instancia)

---

### 2. Configurar Detalhes da Instância

- Nome da VM: `myVM`
- Imagem: `Windows Server 2022 Datacenter: Azure Edition - x64 Gen 2`
- Região e tamanho: mantenha os padrões.

📌 Alguns usuários podem ter a opção de **zonas de disponibilidade**.

---

### 3. Conta de Administrador

- Nome de usuário: `azureuser`
- Senha: mínimo de 12 caracteres, com complexidade.

![Conta de Administrador](https://via.placeholder.com/800x400?text=Conta+de+Administrador)

---

### 4. Regras de Porta de Entrada

- Permitir portas selecionadas:
  - ✅ RDP (3389)
  - ✅ HTTP (80)

![Regras de Porta](https://via.placeholder.com/800x400?text=Regras+de+Porta)

---

### 5. Criar a VM

- Clique em **Examinar + criar**
- Após validação, clique em **Criar**

![Examinar e Criar](https://via.placeholder.com/800x400?text=Examinar+e+Criar)

---

## 🔗 Conectar-se à Máquina Virtual

1. Vá para a VM no portal e clique em **Conectar > RDP**  
2. Baixe o arquivo `.rdp`  
3. Abra o arquivo e clique em **Conectar**  
4. Clique em **Mais opções > Usar uma conta diferente**  
   - Nome de usuário: `localhost\nome_de_usuário`  
   - Senha: conforme definido  

⚠️ Pode aparecer um aviso de certificado — clique em **Sim** para continuar.

![Conectar RDP](https://via.placeholder.com/800x400?text=Conectar+via+RDP)

---

## 🌐 Instalar o Servidor Web IIS

No PowerShell da VM, execute:

```powershell
Install-WindowsFeature -name Web-Server -IncludeManagementTools
```

---

## 📄 Ver a Página de Boas-vindas do IIS

1. Copie o IP público da VM
2. Cole em uma nova aba do navegador

Você verá a página padrão do IIS:

![Página do IIS](https://via.placeholder.com/800x400?text=Pagina+do+IIS)

---

## 🧹 Limpar os Recursos

1. No portal da VM, clique no **Grupo de Recursos**
2. Selecione **Excluir grupo de recursos**
3. Digite o nome e clique em **Excluir**

---

## 🕒 Configurar Desligamento Automático

1. Vá para **Operações > Desligamento automático**
2. Ative e defina o horário desejado
3. Clique em **Salvar**

📌 Lembre-se de ajustar o **fuso horário** corretamente (UTC por padrão).

---

## 📚 Próximas Etapas

Explore mais sobre VMs no Azure:

👉 [Documentação Oficial da Microsoft](https://learn.microsoft.com/azure/virtual-machines/windows/)

