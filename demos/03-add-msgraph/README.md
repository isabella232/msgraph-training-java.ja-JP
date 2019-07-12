---
ms.openlocfilehash: a890c296f4269b674356118463578c9b79001b0e
ms.sourcegitcommit: 02054b307013cce781be2a3512ec1e54f1a322eb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2019
ms.locfileid: "35634718"
---
# <a name="how-to-run-the-completed-project"></a>完了したプロジェクトを実行する方法

## <a name="prerequisites"></a>前提条件

このフォルダーで完了したプロジェクトを実行するには、次のものが必要です。

- 開発用コンピューターにインストールされている[JAVA SE 開発キット (JDK)](https://java.com/en/download/faq/develop.xml)と[Maven](https://maven.apache.org/) 。 JDK または Maven を持っていない場合は、「ダウンロードオプション」の前のリンクにアクセスしてください。 (**注:** このチュートリアルは、openjdk バージョン12.0.1 および Maven 3.6.1 を使用して記述されています。 このガイドの手順は、他のバージョンでは動作しますが、テストされていません。)
- Microsoft 職場または学校のアカウント。

Microsoft アカウントを持っていない場合は、 [office 365 開発者プログラムにサインアップ](https://developer.microsoft.com/office/dev-program)して、無料の office 365 サブスクリプションを取得することができます。

## <a name="register-a-web-application-with-the-azure-active-directory-admin-center"></a>Web アプリケーションを Azure Active Directory 管理センターに登録する

1. ブラウザーを開き、[Azure Active Directory 管理センター](https://aad.portal.azure.com)に移動します。 **個人用アカウント** (別名: Microsoft アカウント)、または**職場/学校アカウント**を使用してログインします。

1. 左側のナビゲーションで [ **Azure Active Directory** ] を選択し、[**管理**] の下にある [**アプリの登録**] を選択します。

    ![アプリの登録のスクリーンショット ](/tutorial/images/aad-portal-app-registrations.png)

1. **[新規登録]** を選択します。 **[アプリケーションを登録]** ページで、次のように値を設定します。

    - `Java Graph Tutorial` に **[名前]** を設定します。
    - **サポートされているアカウントの種類**を**任意の組織ディレクトリのアカウント**に設定します。
    - **[リダイレクト URI]** を空のままにします。

    ![[アプリケーションの登録] ページのスクリーンショット](/tutorial/images/aad-register-an-app.png)

1. [**登録**] を選択します。 [ **Java Graph のチュートリアル**] ページで、**アプリケーション (クライアント) ID**の値をコピーして保存します。次の手順で必要になります。

    ![新しいアプリの登録のアプリケーション ID のスクリーンショット](/tutorial/images/aad-application-id.png)

1. [**リダイレクト URI を追加する**] リンクを選択します。 [**リダイレクト uri** ] ページで、[**パブリッククライアント (モバイル、デスクトップ)] セクションの推奨されるリダイレクト uri**を見つけます。 `https://login.microsoftonline.com/common/oauth2/nativeclient` URI を選択します。

    ![リダイレクト Uri ページのスクリーンショット](/tutorial/images/aad-redirect-uris.png)

1. [**既定のクライアントの種類**] セクションを探し、[アプリケーションを**パブリッククライアントとして扱う**] を [**はい**] に変更して、[**保存**] を選択します。

    ![[既定のクライアントの種類] セクションのスクリーンショット](/tutorial/images/aad-default-client-type.png)

## <a name="configure-the-sample"></a>サンプルを構成する

1. ファイルの`oAuth.properties.example`名前を`oAuth.properties`に変更します。
1. `oAuth.properties`ファイルを編集し、次のように変更します。
    1. を`YOUR_APP_ID_HERE`アプリ登録ポータルで取得した**アプリケーション Id**に置き換えます。

## <a name="build-and-run-the-sample"></a>サンプルの構築と実行

コマンドラインインターフェイス (CLI) で、プロジェクトディレクトリに移動し、次のコマンドを実行します。

```Shell
mvn package
java -cp target/graphtutorial-1.0-SNAPSHOT.jar com.contoso.App
```
