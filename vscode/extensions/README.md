# How to sync list of vscode extensions?

## Step1: Export list of extensions

```bash
code --list-extensions > vscode-extension.txt
```

## Step2: Write extension installation script

```bash
# ./vscode-install.sh
BASE_DIR=$(dirname "$0")
EXTENSION_IDENTIFIERS=$(cat "${BASE_DIR}/vscode-extension.txt")

echo "<Installing packages..🚀>"

for identifier in $EXTENSION_IDENTIFIERS
do
    echo $(code --install-extension $identifier)
done
```

## Step3: Run extension installation script

```
sh ./vscode-install.sh
```
