# PPMEのデータバックアップ、リストアガイド

PPME登録のPrinter List/ Profile / Tags などのデータをバックアップ・リストアするためのガイド。

</br>


## ■ PPME 3.4のバックアップ

</br>

###  サービスの停止

***[重要] サービス停止中はPPMEの利用は不可。運用に影響がないタイミングで実施すること。***

1. タスクマネージャを起動する。
1. 下記サービスを停止する。

    - ppme-service
    - Printer Profile Manager Enterprise Database...

    ![service01](image-9.png)

</br>

###  バックアップ準備

1. コマンドプロンプトを“管理者として実行”で起動する。

1. 下記コマンドを実行する。

        takeown /R /D Y /F "C:\ProgramData\Zebra Technologies\Printer Profile Manager Enterprise"

    </br>

        icacls "C:\ProgramData\Zebra Technologies\Printer Profile Manager Enterprise" /grant:r %username%:(OI)(CI)F /T

    </br>

        icacls "C:\ProgramData\Zebra Technologies\Printer Profile Manager Enterprise\postgresql\14.2-1\data" /grant:r SYSTEM:(OI)(CI)F /T

</br>

###  データのバックアップ

1. 下記フォルダを任意のフォルダーにコピーする。

        “C:\ProgramData\Zebra Technologies\Printer Profile Manager Enterprise”

    </br>

        “C:\Program Files\Zebra Technologies\Printer Profile Manager Enterprise”

</br>

###  サービスの起動

1. タスクマネージャを起動する。
1. 下記サービスを起動する。

    - ppme-service
    - Printer Profile Manager Enterprise Database...

    ※ サービス開始後、PPMEが利用可能まで少し時間がかかる。

</br></br>



## ■ PPME 3.4のリストア

</br>

###  サービスの停止

***[重要] サービス停止中はPPMEの利用は不可。運用に影響がないタイミングで実施すること。***

1. タスクマネージャを起動する。
1. 下記サービスを停止する。

    - ppme-service
    - Printer Profile Manager Enterprise Database...

    ![service01](image-9.png)

</br>

###  リストア準備

1. コマンドプロンプトを“管理者として実行”で起動する。

1. 下記コマンドを実行する。

        takeown /R /D Y /F "C:\ProgramData\Zebra Technologies\Printer Profile Manager Enterprise"

    </br>

        icacls "C:\ProgramData\Zebra Technologies\Printer Profile Manager Enterprise" /grant:r %username%:(OI)(CI)F /T

    </br>

        icacls "C:\ProgramData\Zebra Technologies\Printer Profile Manager Enterprise\postgresql\14.2-1\data" /grant:r SYSTEM:(OI)(CI)F /T


</br>

###  データのリストア

1. 予めバックアップしたフォルダを下記フォルダにコピー。

        “C:\ProgramData\Zebra Technologies\Printer Profile Manager Enterprise”

    </br>

        “C:\Program Files\Zebra Technologies\Printer Profile Manager Enterprise”

</br>

###  サービスの起動

1. タスクマネージャを起動する。
1. 下記サービスを起動する。

    - ppme-service
    - Printer Profile Manager Enterprise Database...

    ※ サービス開始後、PPMEが利用可能まで少し時間がかかる。

1. PPME動作確認とデータ反映確認をする。


