---
title: GitHub アカウントへの新しい SSH キーの追加
intro: 'To configure your account on {% ifversion ghae %}{% data variables.product.product_name %}{% else %}{% data variables.product.product_location %}{% endif %} to use your new (or existing) SSH key, you''ll also need to add the key to your account.'
redirect_from:
  - /articles/adding-a-new-ssh-key-to-your-github-account
  - /github/authenticating-to-github/adding-a-new-ssh-key-to-your-github-account
  - /github/authenticating-to-github/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account
versions:
  fpt: '*'
  ghes: '*'
  ghae: '*'
  ghec: '*'
topics:
  - SSH
shortTitle: Add a new SSH key
---

## About addition of SSH keys to your account

{% data reusables.ssh.about-ssh %} For more information, see "[About SSH](/authentication/connecting-to-github-with-ssh/about-ssh)."

After you generate an SSH key pair, you must add the public key to {% ifversion fpt or ghec or ghes %}{% data variables.product.product_location %}{% elsif ghae %}{% data variables.product.product_name %}{% endif %} to enable SSH access for your account.

## 必要な環境

Before adding a new SSH key to your account on {% ifversion ghae %}{% data variables.product.product_name %}{% else %}{% data variables.product.product_location %}{% endif %}, complete the following steps.

1. Check for existing SSH keys. For more information, see "[Checking for existing SSH keys](/authentication/connecting-to-github-with-ssh/checking-for-existing-ssh-keys)."
1. Generate a new SSH key and add it to your machine's SSH agent. 詳しい情報については、「[新しい SSH キーを生成して ssh-agent に追加する](/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)」を参照してください。

## Adding a new SSH key to your account

After adding a new SSH key to your account on {% ifversion ghae %}{% data variables.product.product_name %}{% else %}{% data variables.product.product_location %}{% endif %}, you can reconfigure any local repositories to use SSH. 詳しい情報については[リモート URL の HTTPS から SSH への切り替え](/github/getting-started-with-github/managing-remote-repositories/#switching-remote-urls-from-https-to-ssh)を参照してください。

{% data reusables.ssh.key-type-support %}

{% mac %}

{% webui %}

1. SSH 公開鍵をクリップボードにコピーします。

  SSH 公開鍵のファイル名がサンプルコードと異なる場合は、現在の設定に一致するようにファイル名を変更してください。 キーをコピーする際には、改行や空白を追加しないでください。

  ```shell
  $ pbcopy &lt; ~/.ssh/id_{% ifversion ghae %}rsa{% else %}ed25519{% endif %}.pub
  # Copies the contents of the id_{% ifversion ghae %}rsa{% else %}ed25519{% endif %}.pub file to your clipboard
  ```

  {% tip %}

  **ヒント:** `pbcopy` がうまく動作しない場合は、隠れフォルダ `.ssh` にアクセスし、使い慣れたテキストエディタでこのファイルを開き、クリップボードにコピーしてください。

  {% endtip %}

{% data reusables.user-settings.access_settings %}
{% data reusables.user-settings.ssh %}
4. [**New SSH key**] または [**Add SSH key**] をクリックします。 ![SSH キーボタン](/assets/images/help/settings/ssh-add-ssh-key.png)
5. [Title] フィールドで、新しいキーを説明するラベルを追加します。 たとえば、個人のMacを使っているなら、このキーを「Personal MacBook Air」とすることができるでしょう。
6. キーを [Key] フィールドに貼り付けます。 ![キーフィールド](/assets/images/help/settings/ssh-key-paste.png)
7. **[Add SSH key]** をクリックしてください。 ![キーの追加ボタン](/assets/images/help/settings/ssh-add-key.png)
{% data reusables.user-settings.sudo-mode-popup %}

{% endwebui %}

{% endmac %}

{% windows %}

{% webui %}

1. SSH 公開鍵をクリップボードにコピーします。

  SSH 公開鍵のファイル名がサンプルコードと異なる場合は、現在の設定に一致するようにファイル名を変更してください。 キーをコピーする際には、改行や空白を追加しないでください。

  ```shell
  $ clip &lt; ~/.ssh/id_{% ifversion ghae %}rsa{% else %}ed25519{% endif %}.pub
  # Copies the contents of the id_{% ifversion ghae %}rsa{% else %}ed25519{% endif %}.pub file to your clipboard
  ```

  {% tip %}

  **ヒント:** `clip` がうまく動作しない場合は、隠しフォルダ `.ssh` にアクセスし、使い慣れたテキストエディタでこのファイルを開き、クリップボードにコピーしてください。

  {% endtip %}

{% data reusables.user-settings.access_settings %}
{% data reusables.user-settings.ssh %}
4. [**New SSH key**] または [**Add SSH key**] をクリックします。 ![SSH キーボタン](/assets/images/help/settings/ssh-add-ssh-key.png)
5. [Title] フィールドで、新しいキーを説明するラベルを追加します。 たとえば、個人のMacを使っているなら、このキーを「Personal MacBook Air」とすることができるでしょう。
6. キーを [Key] フィールドに貼り付けます。 ![キーフィールド](/assets/images/help/settings/ssh-key-paste.png)
7. **[Add SSH key]** をクリックしてください。 ![キーの追加ボタン](/assets/images/help/settings/ssh-add-key.png)
{% data reusables.user-settings.sudo-mode-popup %}

{% endwebui %}

{% endwindows %}

{% linux %}

{% webui %}

1. SSH 公開鍵をクリップボードにコピーします。

  SSH 公開鍵のファイル名がサンプルコードと異なる場合は、現在の設定に一致するようにファイル名を変更してください。 キーをコピーする際には、改行や空白を追加しないでください。

  ```shell
  $ cat ~/.ssh/id_{% ifversion ghae %}rsa{% else %}ed25519{% endif %}.pub
  # Then select and copy the contents of the id_{% ifversion ghae %}rsa{% else %}ed25519{% endif %}.pub file
  # displayed in the terminal to your clipboard
  ```

  {% tip %}

  **Tip:** Alternatively, you can locate the hidden `.ssh` folder, open the file in your favorite text editor, and copy it to your clipboard.

  {% endtip %}

{% data reusables.user-settings.access_settings %}
{% data reusables.user-settings.ssh %}
4. [**New SSH key**] または [**Add SSH key**] をクリックします。 ![SSH キーボタン](/assets/images/help/settings/ssh-add-ssh-key.png)
5. [Title] フィールドで、新しいキーを説明するラベルを追加します。 たとえば、個人のMacを使っているなら、このキーを「Personal MacBook Air」とすることができるでしょう。
6. キーを [Key] フィールドに貼り付けます。 ![キーフィールド](/assets/images/help/settings/ssh-key-paste.png)
7. **[Add SSH key]** をクリックしてください。 ![キーの追加ボタン](/assets/images/help/settings/ssh-add-key.png)
{% data reusables.user-settings.sudo-mode-popup %}

{% endwebui %}

{% endlinux %}

{% cli %}

{% data reusables.cli.cli-learn-more %}

Before you can use the {% data variables.product.prodname_cli %} to add an SSH key to your account, you must authenticate to the {% data variables.product.prodname_cli %}. For more information, see [`gh auth login`](https://cli.github.com/manual/gh_auth_login) in the {% data variables.product.prodname_cli %} documentation.

To add an SSH key to your GitHub account, use the `ssh-key add` subcommand, specifying your public key.

```shell
gh ssh-key add <em>key-file</em>
```

To include a title for the new key, use the `-t` or `--title` flag.

```shell
gh ssh-key add <em>key-file</em> --title "personal laptop"
```

If you generated your SSH key by following the instructions in "[Generating a new SSH key](/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)", you can add the key to your account with this command.

```shell
gh ssh-key add ~/.ssh/id_ed25519.pub
```

{% endcli %}

{% ifversion fpt or ghec %}
## 参考リンク

- [SAMLシングルサインオンで使うためにSSHキーを認可する](/articles/authorizing-an-ssh-key-for-use-with-saml-single-sign-on)
{% endif %}
