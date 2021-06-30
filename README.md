# Completion for lacework
This script is to be use with zsh and can be use with Oh My Zsh framework to get lacework command completion.
Oh My Zsh is a delightful, open source, community-driven framework for managing your Zsh configuration that you can get from https://ohmyz.sh/

## Instalation
To use the lacework completion with Zsh (without Oh My Zsh):
  1. Just drop the file in one of your function folders that you can find looking in fpath: `echo $fpath`

To use the lacework completion with Oh My Zsh you need to:
  1. create directory ~/.oh-my-zsh/custom/plugins/lacework
  2. copy the file in _lacework in the directory ~/.oh-my-zsh/custom/plugins/lacework
  3. edit your ~/.zshrc file, find the line starting by plugins to add lacework to the plugins list, you should at least have: `plugins=(lacemork)`
 
This has been tested with cli version 0.9.1

## Information on some completion
to be done
