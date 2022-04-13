---
title: Abilitare Teams Rooms dispositivi per partecipare a riunioni di terze parti
ms.author: czawideh
author: cazawideh
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
description: Questo articolo descrive come configurare l'organizzazione e Teams Rooms dispositivi per supportare la partecipazione a riunioni di terze parti a Cisco WebEx e Zoom.
ms.openlocfilehash: 04be17003e39890ba74d6c7c4fc2393ba809f5c6
ms.sourcegitcommit: 3beef904411a9d5787a73678464003a868630649
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/12/2022
ms.locfileid: "64817667"
---
# <a name="enable-teams-room-devices-to-join-third-party-meetings"></a>Abilitare Teams dispositivi sala per partecipare a riunioni di terze parti

Microsoft Teams Rooms dispositivi supportano un'esperienza con un tocco per partecipare a riunioni online di terze parti, dette anche partecipazione diretta degli utenti guest. Se abilitata, è possibile usare Teams Rooms per partecipare a riunioni ospitate su Cisco WebEx e Zoom con la facilità con cui è possibile partecipare a riunioni ospitate in Microsoft Teams.

Prima di partecipare a riunioni di terze parti da Teams Rooms, è necessario eseguire le operazioni seguenti:

1. Configurare la cassetta postale della sala Exchange Online del Teams Rooms per elaborare gli inviti alle riunioni di terze parti.
2. Assicurarsi che l'organizzazione non abbia criteri che impediscano la connessione ai servizi per riunioni di terze parti.
3. Configurare Teams Rooms per consentire riunioni di terze parti.

Le sezioni seguenti illustrano come eseguire ognuna di queste operazioni.

## <a name="step-1-allow-calendar-invite-processing-for-third-party-meetings"></a>Passaggio 1: Consentire l'elaborazione degli inviti al calendario per le riunioni di terze parti

La prima cosa da fare per abilitare un'esperienza di partecipazione con un tocco da Gruppi di team è impostare le regole di elaborazione del calendario per la cassetta postale della sala Exchange Online del dispositivo. La cassetta postale della sala deve consentire le riunioni esterne e mantenere il corpo e l'oggetto del messaggio in modo che possa vedere l'URL necessario per partecipare alla riunione di terze parti. Per impostare queste opzioni della cassetta postale della sala utilizzando il cmdlet [Set-CalendarProcessing](/powershell/module/exchange/set-calendarprocessing?view=exchange-ps.) , eseguire le operazioni seguenti:

1. Connessione a Exchange Online PowerShell. Per altre informazioni, vedere [Connessione a Exchange Online PowerShell con autenticazione di base](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps) o [Connessione per Exchange Online PowerShell con l'autenticazione a più](/powershell/exchange/mfa-connect-to-exchange-online-powershell?view=exchange-ps) fattori, a seconda del metodo di autenticazione.

2. Ottenere il nome dell'entità utente (UPN) della cassetta postale della sala, se non lo si conosce eseguendo il comando seguente:

    ```powershell
    Get-Mailbox | Where {$_.RoomMailboxAccountEnabled -eq $True} | Format-Table Name, UserPrincipalName
    ```
    
3. Trovare il nome della cassetta postale della sala associata al dispositivo Teams Rooms e prendere nota dell'UPN.

4. Dopo aver trovato l'UPN della cassetta postale della sala, eseguire il comando seguente. Sostituire `<UserPrincipalName>` con l'UPN della cassetta postale della sala:

    ```powershell
    Set-CalendarProcessing <UserPrincipalName> -ProcessExternalMeetingMessages $True -DeleteComments $False -DeleteSubject $False
    ```

Altre informazioni su [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell?view=exchange-ps).

## <a name="step-2-configure-office-365-threat-protection-and-link-rewrite"></a>Passaggio 2: Configurare Office 365 Threat Protection e riscrivere i collegamenti

Per abilitare l'esperienza di partecipazione con un tocco, le informazioni sul collegamento di partecipazione alla riunione di terze parti devono essere presenti e leggibili nell'invito alla riunione. Se l'organizzazione usa la funzionalità [Microsoft Defender per Office 365](/microsoft-365/security/office-365-security/safe-links?view=o365-worldwide) collegamenti sicuri o se si usa una soluzione di terze parti che analizza tutti gli URL in arrivo e in uscita alla ricerca di minacce, potrebbe modificare gli URL di partecipazione alla riunione e rendere la riunione non riconoscibile dal dispositivo Teams Rooms. Per assicurarsi che ciò non accada, è necessario aggiungere gli URL del servizio di riunione di terze parti a Defender for [Office 365 Cassaforte Links **Non riscrivere** elenco o l'elenco di eccezioni di riscrittura](/microsoft-365/security/office-365-security/safe-links?view=o365-worldwide) URL di terze parti.

 Se si usa una soluzione di terze parti, vedere le istruzioni per la soluzione per aggiungere URL al relativo elenco di eccezioni di riscrittura URL.

Ecco alcune voci di esempio che potrebbe essere necessario aggiungere all'elenco Defender per Office 365 Cassaforte Collegamenti *non riscrivere* o all'elenco di eccezioni di riscrittura URL di terze parti:

- **Cisco WebEx** `*.webex.com*`
- **Zoom** `*.zoom.us*`, `*.zoom.com*``*.zoomgov.com*`

Per un elenco completo degli URL da aggiungere all'elenco collegamenti Defender per Office 365 Cassaforte *Non riscrivere* o all'elenco di eccezioni di riscrittura URL di terze parti, contattare il provider di servizi per riunioni di terze parti da cui accettare inviti alle riunioni.

> [!CAUTION]
> Aggiungere solo gli URL attendibili all'elenco collegamenti di Microsoft Defender per Office 365 Cassaforte *Non riscrivere* o all'elenco di eccezioni di riscrittura URL di terze parti.

## <a name="step-3-enable-third-party-meetings-on-teams-rooms"></a>Passaggio 3: Abilitare le riunioni di terze parti in Teams Rooms

L'ultimo passaggio da eseguire è consentire a Teams Rooms di partecipare a riunioni di terze parti. Le riunioni di terze parti richiedono un nome utente e un indirizzo di posta elettronica per partecipare. Se il nome utente e l'indirizzo di posta elettronica da usare sono diversi dalla cassetta postale della sala del dispositivo, è necessario aggiungerli al dispositivo. È possibile eseguire questa operazione nelle impostazioni di Teams Rooms o nel file di configurazione XML.

### <a name="use-device-settings"></a>Usare le impostazioni del dispositivo

Per configurare Teams Rooms utilizzando la console touchscreen, esegui le operazioni seguenti:

1. Nella console Microsoft Teams Rooms seleziona **Altro ...**.
2. Seleziona **Impostazioni** e quindi immetti il nome utente e la password dell'amministratore del dispositivo.
3. Vai alla scheda **Riunioni** e seleziona **Cisco WebEx**, **Zoom** o entrambi.
4. Per partecipare alle riunioni con il nome utente e l'indirizzo di posta elettronica associati alla cassetta postale della sala, selezionare **Partecipa con le informazioni sulla sala**.
5. Se vuoi partecipare alle riunioni con un nome utente alternativo e un indirizzo e-mail, seleziona **Partecipa con info personalizzate** e immetti il nome utente e l'indirizzo e-mail che vuoi usare.
6. Seleziona **Salva e chiudi**. Il dispositivo verrà riavviato.

### <a name="use-the-skypesettingsxml-configuration-file"></a>Usare il file di configurazione SkypeSettings.xml

È possibile aggiungere le impostazioni seguenti al `SkypeSettings.xml` file che si trova in `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState`. Per altre informazioni sul `SkypeSettings.xml` file, vedere [Gestire in remoto le impostazioni di una console Microsoft Teams Rooms con un file di configurazione XML](xml-config-file.md).

Per abilitare le riunioni di Cisco WebEx, impostare l'elemento `WebExMeetingsEnabled` XML su **True**, come indicato di seguito.

```xml
<WebExMeetingsEnabled>True</WebExMeetingsEnabled>
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

> [!NOTE]
> Per partecipare a una riunione Cisco WebEx da un dispositivo Teams Rooms, la riunione Cisco deve essere ospitata in Riunioni WebEx Pro con l'applicazione Web Cisco WebEx versione WBS 40.7 o successiva. 
