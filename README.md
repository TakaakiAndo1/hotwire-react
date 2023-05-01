# Use React with Hotwire

It is a demo that shows how you can plug a react app inside a rails app using Stimulus.js.

If you start the app, and go to the "page with react" you will see a page with the counters implemented using react and started using a Stimulus controller.

By starting the react app with Stimulus.js you can then move back to the index, that don’t have any react component, and the go back to the page with react using turbo, and Stimulus.js will initialize the app as expected.

Like in this video…

[Hotwire with react demo](https://www.loom.com/share/02454214bbbe45ef96cf7a821c64b606?t=0)

## Blog post

I wrote a blog post, explaining how you can integrate react with hotwire, using this repo as example.

You can find it on [bhserna.com/use-react-with-hotwire.html](https://bhserna.com/use-react-with-hotwire.html)

## Versions

### Ruby
* Ruby: 3.0.0
* Rails: 7.0.2.2
* Turbo rails: 1.0.0
* Stimulus rails: 1.0.2

### Javascript
* React: 17.0.2
* React Dom: 17.0.2

### セットアップ手順

1. (RVMを使用して)Ruby 3.0.0をインストール
    ```bash
    xcode-select --install
    brew install gpg
    gpg --keyserver keyserver.ubuntu.com --recv-keys 409B6B1796C275462A1703113804BB82D39DC0E3 7D2BAF1CF37B13E2069D6956105BD0E739499BDB\n
    curl -sSL https://get.rvm.io | bash
    rvm install 3.0.0
    ```
1. データベース(PostgreSQL)をインストール
    ```bash
    brew install postgresql
    brew services restart postgresql
    ```
1. RubyOnRailsの初期セットアップ
    ```bash
    bundle install
    rails db:create
    ```
1. asdf（環境セットアップの支援ツール）のインストールおよびasdfを使ったNode.jsのセットアップ
    ```bash
    brew install coreutils curl git
    git clone https://github.com/asdf-vm/asdf.git ~/.asdf --branch v0.11.3
    brew install asdf
    echo -e "\n. $(brew --prefix asdf)/libexec/asdf.sh" >> ${ZDOTDIR:-~}/.zshrc #zshを使用している場合のコマンドになります。
    brew install gpg gawk
    asdf plugin add nodejs https://github.com/asdf-vm/asdf-nodejs.git
    asdf install
    ```
1. サーバーの起動
    ```bash
    bin/dev
    ```