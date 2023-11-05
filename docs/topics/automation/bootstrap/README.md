## GITOPS HELMRELEASE AUTOMATION

the big 'difference' is that i did something that is either genius or stupid.
I wrote a script to help me move to the new folder structure (it scanned dirs, anything that had files in it byt no app folder had a app folder made and the files moved in it) so i could dump my new folder in and run it.
But why stop there?  ive been getting annoyed at the stupid amount of boilerpate ive had to copy.paste/maintain.
So i noodled with https://github.com/Truxnell/home-cluster/blob/main/tools/app-kustomize-gen.sh
This script:
* recurses the folders.  at the namespace level, it adds a kustomize (with entries)/namespace from template and names it according to folder.  If a entry/app folder has a 'wip' file, it adds it commented with a TODO(i.e. disabled)
* 2nd level - looks at the apps in the namespace and creates a kustomize with 
  * It dynamically looks at each app, and builds a ks.yaml with the right entries (i.e. for my cert manager, it loks at the folders app, issuers, and adds entries for them)
  * If theres a helmrelease file in the folder, it adds a helmrelease healthcheck to the entry
  * if thers a pv in the file, its adds a rook dependsOn
  * if theres a externalsecret, it adds that as a dependsOn
  * if theres a dep file, it adds those as dependenices.
* in the 3rd level, it will generate the helmrelease name based on folder so its automatically aligned
  * in most all files (sans secrets) it will ensure all files with metadata.namespace are aligned to the namespace name (makes renaming a entire folders namespace real easy

## virtualenv reinstall
pip install -U --force-reinstall virtualenv

## ~/.zshrc

## REMOVE node
kubectl delete node XXX
ansible:nuke
