---
title: "Umschließen von Android-Apps mit dem App Wrapping Tool | Microsoft-Dokumentation"
description: "In diesem Artikel erfahren Sie, wie Sie Ihre Android-Apps umschließen, ohne den Code der App selbst zu ändern. Bereiten Sie die Apps vor, damit Sie Verwaltungsrichtlinien für mobile Apps anwenden können."
keywords: 
author: mtillman
ms.author: mtillman
manager: angrobe
ms.date: 12/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e9c349c8-51ae-4d73-b74a-6173728a520b
ms.reviewer: oldang
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: ab6d9b6b296fb4e1fb0aaa9496fede28976728dc
ms.openlocfilehash: a89c2b26daf2b3b4da57e0c190f772e078681bee
ms.lasthandoff: 04/14/2017


---

# <a name="prepare-android-apps-for-mobile-application-management-with-the-intune-app-wrapping-tool"></a>Vorbereiten von Android-Apps für die Verwaltung von mobilen Anwendungen mit dem Intune App Wrapping Tool

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Verwenden Sie das Microsoft Intune App Wrapping Tool für Android zum Ändern des Verhaltens Ihrer internen Android-Apps, indem Sie die Features der App einschränken, ohne den eigentlichen Code der App zu ändern.

Das Tool ist eine Windows-Befehlszeilenanwendung, die in PowerShell ausgeführt wird und einen Wrapper um die Android-App erstellt. Nachdem der Wrapper um die App erstellt wurde, können Sie die App-Funktionalität ändern, indem Sie in Intune [Verwaltungsrichtlinien für mobile Anwendungen](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md) konfigurieren.


Lesen Sie vor dem Ausführen des Tools die [Sicherheitsüberlegungen für das Ausführen des App Wrapping Tools](#security-considerations-for-running-the-app-wrapping-tool). Sie können das Tool von der GitHub-Seite [Microsoft Intune App Wrapping Tool for Android](https://github.com/msintuneappsdk/intune-app-wrapping-tool-android) herunterladen.



## <a name="fulfill-the-prerequisites-for-using-the-app-wrapping-tool"></a>Erfüllen der Voraussetzungen zur Verwendung des App Wrapping Tools

-   Sie müssen das App Wrapping Tool auf einem Windows-Computer unter Windows 7 oder höher ausführen.

-   Die Eingabe-App muss ein gültiges Android-Anwendungspaket mit der Dateierweiterung „APK“ sein und folgende Kriterien aufweisen:

    -   Darf nicht verschlüsselt sein.
    -   Darf nicht zuvor bereits vom Intune App Wrapping Tool umschlossen worden sein.
    -   Muss für Android 4.0 oder höher geschrieben sein.

-   Die App muss von Ihrem oder für Ihr Unternehmen entwickelt werden. Sie können dieses Tool nicht für aus dem Google Play Store heruntergeladene Apps verwenden.

-   Um das App Wrapping Tool auszuführen, müssen Sie die neueste Version der [Java Runtime Environment](http://java.com/download/) installieren und sicherstellen, dass die Java-Pfadvariable in den Windows-Umgebungsvariablen auf C:\ProgramData\Oracle\Java\javapath festgelegt wurde. Weitere Informationen finden Sie in der [Java-Dokumentation](http://java.com/download/help/).

    > [!NOTE]
    > In einigen Fällen kann die 32-Bit-Version von Java zu Speicherproblemen führen. Es ist eine gute Idee, die 64-Bit-Version zu installieren.

- Für Android müssen alle App-Pakete (APK-Dateien) signiert sein. Verwenden Sie das Java-Keytool, um Anmeldeinformationen zu generieren, die zum Signieren der umschlossenen Ausgabe-App erforderlich sind. Der folgende Befehl verwendet z.B. die ausführbare Java-Datei „keytool.exe“, um Schlüssel zu generieren, die vom App Wrapping-Tool zum Signieren der umschlossenen Ausgabe-App verwendet werden können.

    ```
    keytool.exe -genkeypair -v -keystore mykeystorefile -alias mykeyalias -keyalg RSA -keysize 2048 -validity 50000
    ```
    Dieses Beispiel verwendet den RSA-Algorithmus, um ein Schlüsselpaar (einen öffentlichen Schlüssel und einen zugehörigen privaten Schlüssel mit einer Länge von 2.048 Bits) zu generieren. Danach wird der öffentliche Schlüssel von einem selbstsignierten X.509 v3-Zertifikat umschlossen, das als Zertifikatkette mit einem Element gespeichert wird. Diese Zertifikatkette und der private Schlüssel werden in einem neuen Keystore-Eintrag namens „mykeystorefile“ gespeichert und durch das Alias „mykeyalias“ identifiziert. Der Keystore-Eintrag ist für 50.000 Tage gültig.

    Der Befehl wird Sie auffordern, Kennwörter für den Keystore und den Schlüssel bereitzustellen. Verwenden Sie sichere Kennwörter. Notieren Sie sich diese Kennwörter jedoch, denn sie werden benötigt, um das App Wrapping Tool auszuführen.

    Für eine ausführliche Dokumentation lesen Sie mehr über das Java-[Keytool](http://docs.oracle.com/javase/6/docs/technotes/tools/windows/keytool.html) und den Java-[Keystore](https://docs.oracle.com/javase/7/docs/api/java/security/KeyStore.html) auf der Oracle-Dokumentationswebsite.

## <a name="install-the-app-wrapping-tool"></a>Installieren des App Wrapping Tools

1.  Laden Sie die Installationsdatei „InstallAWT.exe“ für das Intune App Wrapping Tool für Android aus dem [GitHub-Repository](https://github.com/msintuneappsdk/intune-app-wrapping-tool-android) auf einen Windows-Computer herunter. Öffnen Sie die Installationsdatei.

2.  Akzeptieren Sie den Lizenzvertrag, und schließen Sie die Installation ab.

Merken Sie sich den Ordner, in dem Sie das Tool installieren. Der Standardspeicherort lautet: C:\Programme (x86)\Microsoft Intune Mobile Application Management\Android\App Wrapping Tool.

## <a name="run-the-app-wrapping-tool"></a>Ausführen des App Wrapping Tools

1.  Öffnen Sie auf dem Windows-Computer, auf dem Sie das App Wrapping Tool installiert haben, ein PowerShell-Fenster im Administratormodus.

2.  Importieren Sie das PowerShell-Modul des App Wrapping Tools aus dem Ordner, in dem Sie das Tool installiert haben:

    ```
    Import-Module .\IntuneAppWrappingTool.psm1
    ```

3.  Führen Sie das Tool mit dem Befehl **invoke-AppWrappingTool** aus, der die folgende Verwendungssyntax aufweist:
    ```
    Invoke-AppWrappingTool [-InputPath] <String> [-OutputPath] <String> -KeyStorePath <String> -KeyStorePassword <SecureString>
    -KeyAlias <String> -KeyPassword <SecureString> [-SigAlg <String>] [<CommonParameters>]
    ```

 Die folgende Tabelle führt die Eigenschaften des Befehls **invoke-AppWrappingTool** auf:

|Eigenschaft|Informationen|Beispiel|
|-------------|--------------------|---------|
|**-InputPath**&lt;String&gt;|Pfad der Android-Quelle-App (.apk).| |
|**-OutputPath**&lt;String&gt;|Pfad zur Android-Ausgabe-App. Ist dies der gleiche Verzeichnispfad wie InputPath, schlägt das Verpacken fehl.| |
|**-KeyStorePath**&lt;String&gt;|Pfad zur Keystoredatei, die das öffentliche/private Schlüsselpaar zum Signieren enthält.|Standardmäßig werden Keystoredateien unter „C:\Programme (x86)\Java\jreX.X.X_XX\bin“ gespeichert. |
|**-KeyStorePassword**&lt;SecureString&gt;|Das Kennwort zum Entschlüsseln des KeyStore. Für Android müssen alle Anwendungspakete (APK-Dateien) signiert sein. Verwenden Sie das Java-Keytool, um das KeyStorePassword zu generieren. Weitere Informationen über den Java-[Keystore](https://docs.oracle.com/javase/7/docs/api/java/security/KeyStore.html) finden Sie hier.| |
|**-KeyAlias**&lt;String&gt;|Der Name des Schlüssels, der zum Signieren verwendet werden soll.| |
|**-KeyPassword**&lt;SecureString&gt;|Das Kennwort zum Entschlüsseln des privaten Schlüssels, der zum Signieren verwendet wird.| |
|**-SigAlg**&lt;SecureString&gt;| (Optional) Der Name des Signaturalgorithmus, der zum Signieren verwendet werden soll. Der Algorithmus muss mit dem privaten Schlüssel kompatibel sein.|Beispiele: SHA256withRSA, SHA1withRSA, MD5withRSA|
| **&lt;CommonParameters&gt;** | (Optional) Der Befehl unterstützt allgemeine PowerShell-Parameter, wie z.B. „verbose“ und „debug“. |


- Eine Liste der allgemeinen Parameter finden Sie im [Microsoft Script Center](https://technet.microsoft.com/library/hh847884.aspx).

- Um ausführliche Informationen zu dem Tool zu erhalten, geben Sie folgenden Befehl ein:

    ```
    Help Invoke-AppWrappingTool
    ```

**Beispiel:**

Importieren Sie das PowerShell-Modul.
```
Import-Module "C:\Program Files (x86)\Microsoft Intune Mobile Application Management\Android\App Wrapping Tool\IntuneAppWrappingTool.psm1"
```
Führen Sie das App Wrapping Tool in der nativen App „HelloWorld.apk“ aus.
```
invoke-AppWrappingTool -InputPath .\app\HelloWorld.apk -OutputPath .\app_wrapped\HelloWorld_wrapped.apk -KeyStorePath "C:\Program Files (x86)\Java\jre1.8.0_91\bin\mykeystorefile" -keyAlias mykeyalias -SigAlg SHA1withRSA -Verbose
```

Sie werden zur Eingabe von **KeyStorePassword** und **KeyPassword**aufgefordert. Geben Sie die Anmeldeinformationen ein, die Sie zum Erstellen der Keystore-Datei verwendet haben.

Es wird sowohl die umschlossene App als auch eine Protokolldatei generiert und in dem von Ihnen angegebenen Ausgabepfad gespeichert.

## <a name="security-considerations-for-running-the-app-wrapping-tool"></a>Sicherheitsüberlegungen zum Ausführen des App Wrapping Tools
So verhindern Sie ein mögliches Spoofing, das Offenlegen von Informationen und Angriffe durch Rechteerweiterungen:

-   Stellen Sie sicher, dass sich die Branchenanwendung für die Eingabe, die Ausgabeanwendung und der Java-Keystore auf demselben Windows-Computer befinden, auf dem auch das App Wrapping Tool ausgeführt wird.

-   Importieren Sie die Ausgabeanwendung in die Intune-Konsole auf demselben Computer, auf dem das Tool ausgeführt wird. Weitere Informationen zum Java-Keytool finden Sie unter [Keytool](https://docs.oracle.com/javase/8/docs/technotes/tools/unix/keytool.html).

-   Wenn sich die Ausgabeanwendung und das Tool in einem UNC-Pfad (Universal Naming Convention) befinden und Sie das Tool und die Eingabedateien nicht auf demselben Computer ausführen, sichern Sie die Umgebung, indem Sie [Internet Protocol Security (IPsec)](http://wikipedia.org/wiki/IPsec) oder [SMB-Signaturen (Server Message Block)](https://support.microsoft.com/kb/887429) einrichten.

-   Stellen Sie sicher, dass die Anwendung von einer vertrauenswürdigen Quelle stammt.

-   Sichern Sie das Ausgabeverzeichnis, das die umschlossene Anwendung enthält. Erwägen Sie für die Ausgabe ein Verzeichnis auf Benutzerebene zu verwenden.

### <a name="see-also"></a>Weitere Informationen:
- [Auswählen der Vorbereitung von Apps für die mobile Anwendungsverwaltung mit Microsoft Intune](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md)

- [Verwenden des SDK zum Aktivieren von Apps für die Verwaltung von mobilen Anwendungen](use-the-sdk-to-enable-apps-for-mobile-application-management.md)
