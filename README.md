# usuarios365
o que ele faz?
o cliente tem uma unica conta do 365 em varios pcs

1-ele pergunta qual o usuario que esta logado na maquina
2-cria uma pasta com o nome deste usuario e redireciona as pastas de  desktop, meus documentos,imagens e musicas para o one driver.
3-e varias pessoas podem usar uma unica conta contratada do one driver

1-Instalem o one driver
2-Coloque o usuario e senha do one driver
3-Copiem e colem em um arquivo .bat

Obs: coloquem um nome de usuario que corresponda ao usuario que sera usado na maquina, informem este usuario quando rodar o script

Obrigado Charles



@echo off
Echo Digite o nome de usuario deste computador!
set /p nome=nome do usuario = 
echo O nome escolhido foi '%nome%'.
Echo apartir de agora iremos criar pastas no one driver e redirecionar as pastas do computador.

mkdir "%USERPROFILE%\OneDrive\%nome%\MeusArquivos\Desktop"
mkdir "%USERPROFILE%\OneDrive\%nome%\MeusArquivos\Documentos"
mkdir "%USERPROFILE%\OneDrive\%nome%\MeusArquivos\Imagens"
mkdir "%USERPROFILE%\OneDrive\%nome%\MeusArquivos\Videos"


reg.exe add "HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Explorer\User Shell Folders" /v "Desktop" /t REG_SZ /d "%USERPROFILE%\OneDrive\%nome%\MeusArquivos\Desktop" /f
reg.exe add "HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Explorer\User Shell Folders" /v "Personal" /t REG_SZ /d "%USERPROFILE%\OneDrive\%nome%\MeusArquivos\Documentos" /f
reg.exe add "HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Explorer\User Shell Folders" /v "My Pictures" /t REG_SZ /d "%USERPROFILE%\OneDrive\%nome%\MeusArquivos\Imagens" /f
reg.exe add "HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Explorer\User Shell Folders" /v "My Video" /t REG_SZ /d "%USERPROFILE%\OneDrive\%nome%\MeusArquivos\Videos" /f
