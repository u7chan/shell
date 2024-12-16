# shell

カスタムシェル用のリポジトリ

## セットアップ

1. 本リポジトリをクローン
1. リポジトリ配下へ移動

    ```sh
    cd shell
    ```

1. パスの設定

    ubuntu
   
    ```sh
    touch ~/.bash_profile \
    && echo 'export PATH=$PATH:'"$(pwd)" >> ~/.bash_profile \
    && source ~/.bash_profile
    ```

    mac

    ```zsh
    touch ~/.zprofile \
    && echo 'export PATH=$PATH:'"$(pwd)" >> ~/.zprofile \
    && source ~/.zprofile
    ```

1. 新しくターミナルを起動し、以下のコマンドが通ることを確認

    ```sh
    hello
    ```

    実行例

    ```
    $ hello
    hello shell
    ```
