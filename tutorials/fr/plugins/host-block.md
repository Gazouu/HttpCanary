### Blocage des hôtes

**Ce plugin a quelques problèmes dans les anciennes versions, veuillez mettre à jour vers la v3.1.5 et les suivantes**

Le plugin de blocage de l'hôte peut bloquer l'hôte et l'IP spécifiques lors de requêtes sur le réseau. Vous devez configurer l'hôte et l'IP cibles dans /HttpCanary/plugins/HostBlock/hosts.txt. Le fichier sera automatiquement créé lors de l'installation du plugin. Vous pouvez y ajouter ou modifier directement l'hôte et l'adresse IP. Le plugin permet d'utiliser les caractères génériques * et ? pour faire correspondre l'hôte et l'adresse IP.


Voici le format de l'hôte et de l'IP dans hosts.txt:
```
# block the specified QQ domain
xw.qq.com

# block all domains under baidu.com (using wildcard character *)
*.baidu.com

# block the specified IP address
112.25.105.102

# block the IP address between 112.25.105.240 and 112.25.105.249 (using wildcard character ?)
112.25.105.24?

# block the IP address which starts with 223.111 (using wildcard character *)
223.111.*.*
```

Voici un fichier d'hôtes de démonstration :

[Fichier de démonstration](https://raw.githubusercontent.com/MegatronKing/HttpCanary/master/plugins/HostBlock/hosts.txt)