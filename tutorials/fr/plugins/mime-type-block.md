### Blocage de type mime

Le plugin de blocage Mime-Type peut bloquer des requêtes ou des réponses HTTP spécifiques. Vous devez le configurer dans /HttpCanary/plugins/MimeTypeBlock/req-mimes.txt ou res-mimes.txt. Le premier fichier est utilisé pour ajouter des règles de blocage des données de demande, et le second est utilisé pour ajouter des règles de blocage des données de réponse. Ces deux fichiers sont automatiquement créés lors de l'installation du plugin. Vous pouvez ajouter ou modifier le Mime-Type spécifié directement dans ces deux fichiers. La **version v3.1.5** et les versions ultérieures supportent l'utilisation des caractères génériques * et ?

En prenant l'exemple de req-mimes.txt, le format Mime-Type configuré est le suivant:
```
# blocking image requests (using wildcard character *)
image/*

# blocking JSON requests
application/json
```

Voici les exemples de req-mimes.txt et res-mimes.txt:

[Fichier de démonstration](https://raw.githubusercontent.com/MegatronKing/HttpCanary/master/plugins/MimeTypeBlock/req-mimes.txt)

[Fichier de démonstration](https://raw.githubusercontent.com/MegatronKing/HttpCanary/master/plugins/MimeTypeBlock/res-mimes.txt)

Pour en savoir plus sur le Mime-Type, vous pouvez vous référer à
[Liste officielle de type Mime](https://www.iana.org/assignments/media-types/media-types.xhtml)