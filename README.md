# Guia para Criar e Configurar uma Máquina Virtual no Azure

## Entrar no Azure
1. Acesse o [portal do Azure](https://portal.azure.com).

## Criar Máquina Virtual
1. No campo de pesquisa, digite **Máquinas Virtuais**.
2. Em **Serviços**, selecione **Máquinas Virtuais**.
3. Na página **Máquinas Virtuais**, clique em **Criar** e selecione **Máquina Virtual do Azure**.

## Configuração da Máquina Virtual
1. Na seção **Detalhes da Instância**:
   - Insira **myVM** no campo **Nome da Máquina Virtual**.
   - Escolha **Windows Server 2022 Datacenter: Azure Edition - x64 Gen 2** na opção **Imagem**.
   - Deixe as outras configurações como padrão.
   
2. **Conta de Administrador**:
   - Forneça um nome de usuário, por exemplo, **azureuser**.
   - Escolha uma senha que tenha pelo menos 12 caracteres e cumpra os requisitos de complexidade.

3. **Regras de Porta de Entrada**:
   - Selecione **Permitir portas selecionadas**.
   - Escolha **RDP (3389)** e **HTTP (80)**.

4. Deixe os demais padrões e clique em **Examinar + Criar**.
5. Após a validação, clique em **Criar** para implantar a VM.
6. Quando a implantação for concluída, selecione **Ir para o recurso**.

## Conectar-se à Máquina Virtual
1. Na página de visão geral da máquina virtual, selecione **Conectar > RDP**.
2. Na guia **Conectar-se ao RDP**, clique em **Baixar arquivo RDP**.
3. Abra o arquivo baixado e clique em **Conectar**.
4. Na janela **Segurança do Windows**:
   - Selecione **Mais opções > Usar uma conta diferente**.
   - Digite o nome de usuário como **localhost\nome de usuário** e insira a senha criada para a VM.
   - Clique em **OK**.

5. Caso receba um aviso de certificado, selecione **Sim** ou **Continuar**.

## Instalar Servidor Web IIS
1. Abra um prompt do **PowerShell** na VM e execute o comando:
   ```powershell
   Install-WindowsFeature -name Web-Server -IncludeManagementTools
