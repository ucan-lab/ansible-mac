# Ansible Mac

## 事前準備

- GitHub SSH key 設定
- Homebrew インストール
  - https://brew.sh
- Ansible インストール

```
$ brew install ansible

$ ansible --version
ansible [core 2.16.1]
  config file = None
  configured module search path = ['/Users/ucan/.ansible/plugins/modules', '/usr/share/ansible/plugins/modules']
  ansible python module location = /opt/homebrew/Cellar/ansible/9.1.0/libexec/lib/python3.12/site-packages/ansible
  ansible collection location = /Users/ucan/.ansible/collections:/usr/share/ansible/collections
  executable location = /opt/homebrew/bin/ansible
  python version = 3.12.1 (main, Dec  7 2023, 20:45:44) [Clang 15.0.0 (clang-1500.0.40.1)] (/opt/homebrew/Cellar/ansible/9.1.0/libexec/bin/python)
  jinja version = 3.1.2
  libyaml = True
```

## 環境構築

`Ansible Galaxy` からロールのインストールする

```
$ ansible-galaxy install -r requirements.yml
```

`inventory.ini` ファイルを作成する

```
$ cp inventory.ini.example inventory.ini
```

`inventory.ini` ファイルの `ansible_become_user` にユーザー名を入れる

```
$ ansible-playbook playbook.yml -i inventory.ini -K
```
