# Como-fazer-um-redirecionamento-301-de-Dominio-Completo
Como fazer um redirecionamento 301 de Dominio Completo com HTTPS

### passo 1:
crie um .htaccess com:
``RewriteEngine On
RewriteCond %{HTTP_HOST} ^dominioantigo.org$ [NC,OR]
RewriteCond %{HTTP_HOST} ^www.dominioantigo.org$
RewriteCond %{HTTPS} off
RewriteRule ^(.*)$ https://dominionovo.org/$1 [L,R=301]``

### passo 2
crie uma pagina 404.php e coloque um codigo de redirecionamento:
``<meta http-equiv="refresh" content="0;url='https://novodominio.org<?php echo $_SERVER["REQUEST_URI"];?>'">``
