---
title: Abilitare Teams Rooms dispositivi per partecipare a riunioni di terze parti
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: sohailta
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Questo articolo illustra come configurare l'organizzazione e Teams Rooms dispositivi per supportare la partecipazione a riunioni di terze parti a Cisco Webex e Zoom.
ms.openlocfilehash: 23eefeb564e3333b1bc2105a1fc4d57a0ff41bbe
ms.sourcegitcommit: bdb919a6f53556f76dd4a71759412023e6e18fbb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2022
ms.locfileid: "66529678"
---
# <a name="enable-teams-rooms-devices-to-join-third-party-meetings"></a>Abilitare Teams Rooms dispositivi per partecipare a riunioni di terze parti

Microsoft Teams Rooms dispositivi supportano un'esperienza con un tocco per partecipare a riunioni online di terze parti, dette anche partecipazione diretta degli utenti guest. Se abilitata, è possibile usare Teams Rooms per partecipare a riunioni ospitate su Cisco Webex e Zoom con la facilità con cui è possibile partecipare a riunioni ospitate in Microsoft Teams.

Dispositivi e servizi supportati:

- MTR su Windows, tutti i modelli certificati – Zoom, Cisco Webex

- MTR su modelli certificati Android, Poly, Yealink e Logitech - Zoom

> [!NOTE]
> Per partecipare a una riunione Cisco Webex da un dispositivo Teams Rooms, la riunione Cisco deve essere ospitata in Webex Meetings Pro con l'applicazione Web Cisco Webex versione WBS 40.7 o successiva. 

Prima di partecipare a riunioni di terze parti da Teams Rooms, è necessario eseguire le operazioni seguenti:

1. Configurare la cassetta postale della sala Exchange Online del Teams Rooms per elaborare gli inviti alle riunioni di terze parti.
2. Assicurarsi che l'organizzazione non abbia criteri che impediscano la connessione ai servizi per riunioni di terze parti.
3. Configurare Teams Rooms per consentire riunioni di terze parti.

Le sezioni seguenti illustrano come completare ognuno di questi passaggi.

## <a name="step-1-allow-calendar-invite-processing-for-third-party-meetings"></a>Passaggio 1: Consentire l'elaborazione degli inviti al calendario per le riunioni di terze parti

La prima cosa da fare per abilitare un'esperienza di partecipazione con un tocco da Gruppi di team è impostare le regole di elaborazione del calendario per la cassetta postale della sala Exchange Online del dispositivo. La cassetta postale della sala deve consentire le riunioni esterne e mantenere il corpo e l'oggetto del messaggio in modo che possa vedere l'URL necessario per partecipare alla riunione di terze parti. Per impostare queste opzioni della cassetta postale della sala utilizzando il cmdlet [Set-CalendarProcessing](/powershell/module/exchange/set-calendarprocessing.) , eseguire le operazioni seguenti:

1. Connettersi a Exchange Online PowerShell. Per altre informazioni, vedere [Connettersi a Exchange Online PowerShell con l'autenticazione di base](/powershell/exchange/connect-to-exchange-online-powershell) o [Connettersi a Exchange Online PowerShell con l'autenticazione a più](/powershell/exchange/mfa-connect-to-exchange-online-powershell) fattori, a seconda del metodo di autenticazione.

2. Ottenere il nome dell'entità utente (UPN) della cassetta postale della sala, se non lo si conosce eseguendo il comando seguente:

    ```powershell
    Get-Mailbox | Where {$_.RoomMailboxAccountEnabled -eq $True} | Format-Table Name, UserPrincipalName
    ```
    
3. Trovare il nome della cassetta postale della sala associata al dispositivo Teams Rooms e prendere nota dell'UPN.

4. Dopo aver trovato l'UPN della cassetta postale della sala, eseguire il comando seguente. Sostituire `<UserPrincipalName>` con l'UPN della cassetta postale della sala:

    ```powershell
    Set-CalendarProcessing <UserPrincipalName> -ProcessExternalMeetingMessages $True -DeleteComments $False -DeleteSubject $False
    ```

Altre informazioni su [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell).

## <a name="step-2-configure-office-365-threat-protection-and-link-rewrite"></a>Passaggio 2: Configurare Office 365 Threat Protection e riscrivere i collegamenti

Per abilitare l'esperienza di partecipazione con un tocco, le informazioni sul collegamento di partecipazione alla riunione di terze parti devono essere presenti e leggibili nell'invito alla riunione. Se l'organizzazione usa la funzionalità [Microsoft Defender per Office 365](/microsoft-365/security/office-365-security/safe-links) collegamenti sicuri o se si usa una soluzione di terze parti che analizza tutti gli URL in arrivo e in uscita alla ricerca di minacce, potrebbe modificare gli URL di partecipazione alla riunione e rendere la riunione non riconoscibile dal dispositivo Teams Rooms. Per assicurarsi che ciò non accada, è necessario aggiungere gli URL del servizio di riunione di terze parti a Defender per [Office 365 elenco Collegamenti sicuri **Non riscrivere** l'elenco](/microsoft-365/security/office-365-security/safe-links) o l'elenco di eccezioni di riscrittura URL di terze parti.

 Se si usa una soluzione di terze parti, vedere le istruzioni per la soluzione per aggiungere URL al relativo elenco di eccezioni di riscrittura URL.

Ecco alcune voci di esempio che potrebbe essere necessario aggiungere al Defender per Office 365 i collegamenti sicuri *Non riscrivere* l'elenco o l'elenco di eccezioni di riscrittura URL di terze parti:

- **Cisco Webex** `*.webex.com/*`
- **Zoom** `*.zoom.us/*`, `*.zoom.com/*``*.zoomgov.com/*`

Per un elenco completo degli URL da aggiungere al Defender per Office 365 i collegamenti sicuri *Non riscrivere* l'elenco o l'elenco di eccezioni di riscrittura URL di terze parti, contattare il provider di servizi per riunioni di terze parti da cui accettare inviti alle riunioni.

> [!CAUTION]
> Aggiungere solo gli URL attendibili al Microsoft Defender per Office 365 i collegamenti sicuri *Non riscrivere* l'elenco o l'elenco di eccezioni di riscrittura URL di terze parti.

## <a name="step-3a-enable-third-party-meetings-on-teams-rooms-on-windows"></a>Passaggio 3a: Abilitare le riunioni di terze parti in Teams Rooms in Windows

L'ultimo passaggio da eseguire è consentire a Teams Rooms di partecipare a riunioni di terze parti. Le riunioni di terze parti richiedono un nome utente e un indirizzo di posta elettronica per partecipare. Se il nome utente e l'indirizzo di posta elettronica da usare sono diversi dalla cassetta postale della sala del dispositivo, è necessario aggiungerli al dispositivo. È possibile eseguire questa operazione nelle impostazioni di Teams Rooms o nel file di configurazione XML. È possibile eseguire questa operazione nelle impostazioni di Teams Rooms in qualsiasi Teams Rooms che supporta o nel file di configurazione XML per Teams Rooms in Windows.

### <a name="use-device-settings"></a>Usare le impostazioni del dispositivo

Per configurare Teams Rooms in Windows tramite la console touchscreen, esegui le operazioni seguenti:

1. Nella console Microsoft Teams Rooms seleziona **Altro**.
2. Seleziona **Impostazioni** e quindi immetti il nome utente e la password dell'amministratore del dispositivo.
3. Vai alla scheda **Riunioni** e seleziona un provider di riunioni di terze parti che desideri abilitare (ad esempio **Webex**, **Zoom** e così via).
4. Per partecipare alle riunioni con il nome utente e l'indirizzo di posta elettronica associati alla cassetta postale della sala, selezionare **Partecipa con le informazioni sulla sala**.
5. Se vuoi partecipare alle riunioni con un nome utente alternativo e un indirizzo e-mail, seleziona **Partecipa con info personalizzate** e immetti il nome utente e l'indirizzo e-mail che vuoi usare.
6. Seleziona **Salva e chiudi**. Il dispositivo verrà riavviato.

### <a name="use-the-skypesettingsxml-configuration-file"></a>Usare il file di configurazione SkypeSettings.xml

È possibile aggiungere le impostazioni seguenti al `SkypeSettings.xml` file che si trova in `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState`. Per altre informazioni sul `SkypeSettings.xml` file, vedere [Gestire in remoto le impostazioni di una console Microsoft Teams Rooms con un file di configurazione XML](xml-config-file.md).

Per abilitare le riunioni di Cisco Webex, impostare l'elemento `WebexMeetingsEnabled` XML su **True**, come indicato di seguito.

```xml
<WebexMeetingsEnabled>True</WebexMeetingsEnabled>
```

Per abilitare le riunioni con zoom, impostare l'elemento `ZoomMeetingsEnabled` XML su **True**, come indicato di seguito.

```xml
<ZoomMeetingsEnabled>True</ZoomMeetingsEnabled>
```

È possibile specificare facoltativamente un nome utente e un indirizzo di posta elettronica personalizzati per partecipare a riunioni di terze parti usando i seguenti elementi XML. Se i valori specificati non sono validi, il dispositivo Teams Rooms userà per impostazione predefinita il nome utente e l'indirizzo di posta elettronica della cassetta postale della sala.

```xml
<UseCustomInfoForThirdPartyMeetings>true</UseCustomInfoForThirdPartyMeetings>

<CustomDisplayNameForThirdPartyMeetings>guestname</CustomDisplayNameForThirdPartyMeetings>

<CustomDisplayEmailForThirdPartyMeetings>guest@contoso.com</CustomDisplayEmailForThirdPartyMeetings>
```
## <a name="step-3b-enable-third-party-meetings-on-teams-rooms-on-android"></a>Passaggio 3b: Abilitare le riunioni di terze parti in Teams Rooms in Android

Per configurare Teams Rooms su Android tramite la console touchscreen o lo schermo della sala, eseguire le operazioni seguenti:

1.  Sul Microsoft Teams Rooms console o sullo schermo anteriore della sala, seleziona **Altro**.
2.  Selezionare **Impostazioni** e:
    -   Se si usa un account personale, ad esempio un account con una licenza E5, scegliere **l'opzione Riunioni** .
    -   Se si usa un account condiviso (ad esempio un account di risorse con una licenza di Teams Rooms), scegliere **Impostazioni dispositivo**, individuare **Le impostazioni di Teams Amministrazione**, immettere una password di amministratore e scegliere un'opzione **Riunioni**.
      > [!NOTE]
      > Alcuni produttori di dispositivi richiedono una password amministrativa per poter accedere alle **impostazioni del dispositivo** .

    ![Impostazioni delle riunioni per MTR in Android](..\media\mtrandroid.png)

3.  Selezionare un provider di riunioni di terze parti da abilitare.
4.  Se si vuole partecipare a riunioni con un nome utente e un indirizzo di posta elettronica personalizzati, selezionare **Partecipa con nome e indirizzo di posta elettronica personalizzati**. Per aggiornare le informazioni personali personalizzate, premi **Modifica info personalizzate** e inserisci il nome preferito e l'indirizzo e-mail.

