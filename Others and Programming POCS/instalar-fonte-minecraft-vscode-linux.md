## Como instalar fonte (minecraft) no linux e adicionar no VsCode

**1. Fazer download da fonte** -> [FONTE MINECRAFT](https://github.com/IdreesInc/Monocraft/releases); 

**2.**

> cd ~;

**3.**

> mkdir .fonts;

**4.**

> mv Monocraft.otf ~/.fonts/;

**5.** 

> fc-cache -f -v;

**6. Ir nas configurações de fonte do VSCode e adicionar:**

```python
"editor.fontFamily": "Monocraft",
"editor.fontLigatures": true
```

**7. Aplicar as configurações e pronto!**
