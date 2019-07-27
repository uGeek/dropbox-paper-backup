# Dropbox Paper Backup

Download all documents from an Dropbox-Paper account to a local path.

While its very easy to download and maintain a complete copy of your complete Dropbox with tools like [rclone](http://rclone.org/), it's hard to have backups of the documents created in [Dropbox Paper](paper.dropbox.com).

For this reason i wrote this little script to run periodically on my NAS.


# Usage

```
./dropbox-paper-backup.py [--token=TOKEN] [--logfile=PATH] [--verbose] [markdown|html] <target>

Opciones:
  -t --token=TOKEN    El token de acceso para la cuenta de Dropbox. Omitir para obtener una nueva Token
  -l --logfile=PATH   Inicie sesión en el archivo especificado.
  -v --verbose        Se más detallado.
  markdown|html       Exportar ya sea "html" o  "markdown". Hacer ambas cosas si se omite
  <target>            La ruta para almacenar la copia de seguridad en:
```


# Installation

1. Get the script and setup permissions:

  `git clone https://github.com/efenka/dropbox-paper-backup.git`    
  `cd dropbox-paper-backup`    
  `chmod u+x dropbox-paper-backup.py`

2. Install dependencies:

  `pip3 install -r requirements.txt`

3. Create a backup destination and request an authorisation token:

  `./dropbox-paper-backup.py ./archive`

4. Run the script again, giving the token returned by the previous step.

  `./dropbox-paper-backup.py --token=TOKEN ./archive`

Depended on how many files you have, it may take a while.
