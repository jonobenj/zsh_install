ZSH Install
=========

Installs ZSH and configures with OhMyZsh and PowerLevel10k theme, with preconfigured setup. Then makes Zsh the default shell. All done for the user supplied, root creds required to make zsh default for the supplied user.

Role Variables
--------------

| Variable: Default | Function |
|-------------------|----------|
| `omz_install: https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh` | Specifies OhMyZsh source install URL |
| `path_top: $HOME` | Specifies install directory (home dir) |
| `path_omz: '{{ path_top }}/.oh-my-zsh'` | Specifies OhMyZsh install folder path (used for idempotency) |
| `pl10k_src: https://github.com/romkatv/powerlevel10k.git` | Specifies PowerLevel10k git source |
| `pl10k_dest: '{{ path_omz }}/custom/themes/powerlevel10k'` | Specifies install location for PowerLevel10k |
| `pl10k_conf: .p10k.zsh` | Specifies PowerLevel10k config file (stored in this role in files/) |
| `zshrc: .zshrc` |
| `root_required: true` | If you do not have root creds, set this to false. However Zsh will not be made the default shell by this role (must be done manually) |
| `user: "{{ ansible_user }}` | If wanting zsh as default on root user, run the whole playbook as root, and set `user: root`

Example Playbook
----------------

```yaml
---

- name: zsh install
  hosts: all
  tasks:
    - name: install_zsh
      ansible.builtin.include_role:
        name: zsh_install
```

License
-------

BSD

Author Information
------------------

jonob
