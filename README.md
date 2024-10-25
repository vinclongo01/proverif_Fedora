# Comprehensive Guide for installing ProVerif on Fedora

Here’s a step-by-step guide tailored for setting up ProVerif on your Fedora system:

##  Install Dependencies

```bash
sudo dnf update -y
sudo dnf groupinstall "Development Tools" -y   # Equivalent of 'build-essential'
sudo dnf install ocaml ocaml-findlib graphviz gtk2-devel wget tar -y
```
##
Download the `ocaml-lablgtk-devel` Fedora Packages specific for your system (e.g. x86_64) and install them:
```bash
sudo dnf install /path-to-the-rpm-file/ocaml-lablgtk-devel<version>.fc<version>.rpm
```

## Verify the installation
```bash
ocamlfind list | grep lablgtk
```
If `lablgtk` is mentioned in the output everything worked.

## Install Proverif
Download and de-compress ProVerif:
```bash
wget https://bblanche.gitlabpages.inria.fr/proverif/proverif<version>.tar.gz
tar xvf proverif2.05.tar.gz
cd proverif2.05
```
Build ProVerif:
```bash
./build
```

Test ProVerif:
```bash
./test
```

 Copy Executables to Your Path:
 ```bash
sudo cp proverif proverif interact proveriftotex /usr/local/bin/
```

## Verify installation
To verify that ProVerif is installed correctly, you can try running the proverif command:
```bash
proverif --help
```
This should display the help message for ProVerif, confirming that the installation was successful.







