---
title: Abilitare i dispositivi di Teams Rooms per partecipare a riunioni di terze parti
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
localization_priority: Normal
description: Questo articolo illustra come configurare i dispositivi dell'organizzazione e di Teams Room per supportare la partecipazione a riunioni di terze parti a Cisco WebEx e Zoom.
ms.openlocfilehash: 82369c534a616796382b1de69e37c64f15392f9b
ms.sourcegitcommit: db0dc45520503753567e99c0c016f0265d45aa66
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/15/2020
ms.locfileid: "49682385"
---
# <a name="enable-teams-room-devices-to-join-third-party-meetings"></a>Consentire ai dispositivi della sala di Teams di partecipare a riunioni di terze parti

I dispositivi Microsoft Teams Rooms supportano un'esperienza con un solo tocco per partecipare a riunioni online di terze parti, definite anche direct guest join. Se l'opzione è abilitata, è possibile usare un dispositivo Teams Room per partecipare alle riunioni ospitate su Cisco WebEx e Zoom con la facilità con cui è possibile partecipare alle riunioni ospitate in Microsoft Teams.

Prima di poter partecipare a riunioni di terze parti da un dispositivo Teams Room, è necessario eseguire le operazioni seguenti:

1. Configurare la cassetta postale della sala di Exchange Online del dispositivo Teams Rooms per elaborare gli inviti per riunioni di terze parti.
2. Assicurarsi che l'organizzazione non abbia criteri che impedirebbero la connessione ai servizi per riunioni di terze parti.
3. Configurare i dispositivi di Teams Rooms per consentire le riunioni di terze parti.

Le sezioni seguenti illustrano come eseguire ognuno di questi passaggi.

## <a name="step-1-allow-calendar-invite-processing-for-third-party-meetings"></a>Passaggio 1: Consentire l'elaborazione degli inviti al calendario per riunioni di terze parti

La prima cosa da fare per abilitare un'esperienza di partecipazione con un tocco da un dispositivo Team Room è impostare le regole di elaborazione del calendario per la cassetta postale della sala di Exchange Online del dispositivo. La cassetta postale della sala deve consentire le riunioni esterne e mantenere il corpo e l'oggetto del messaggio in modo che possa vedere l'URL necessario per partecipare alla riunione di terze parti. Per impostare queste opzioni della cassetta postale della sala con il cmdlet [Set-CalendarProcessing,](https://docs.microsoft.com/powershell/module/exchange/set-calendarprocessing?view=exchange-ps.) eseguire le operazioni seguenti:

1. Connettersi a PowerShell di Exchange Online. Per altre informazioni, vedere Connettersi a [PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps) di Exchange Online con l'autenticazione di base o Connettersi a [PowerShell di Exchange Online](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell?view=exchange-ps)usando l'autenticazione a più fattori, a seconda del metodo di autenticazione.

2. Ottenere il nome dell'entità utente (UPN) della cassetta postale della chat room se non lo si conosce eseguendo il comando seguente:

    ```powershell
    Get-Mailbox | Where {$_.RoomMailboxAccountEnabled -eq $True} | Format-Table Name, UserPrincipalName
    ```
    
3. Trovare il nome della cassetta postale della sala associata al dispositivo Teams Rooms e prendere nota dell'UPN.

4. Dopo aver trovato l'UPN della cassetta postale della sala, eseguire il comando seguente. Sostituire `<UserPrincipalName>` con l'UPN della cassetta postale della sala:

    ```powershell
    Set-CalendarProcessing <UserPrincipalName> -ProcessExternalMeetingMessages $True -DeleteComments $False -DeleteSubject $False
    ```

Altre informazioni su [PowerShell di Exchange Online.](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell?view=exchange-ps)

## <a name="step-2-configure-office-365-threat-protection-and-link-rewrite"></a>Passaggio 2: Configurare Office 365 Threat Protection e riscrivere i collegamenti

Per consentire l'esperienza di partecipazione con un solo tocco, le informazioni sul collegamento di partecipazione alla riunione provenienti dalla riunione di terze parti devono essere presenti e leggibili nell'invito alla riunione. Se l'organizzazione usa la funzionalità Collegamenti sicuri di [Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links) o se si usa una soluzione di terze parti che analizza tutti gli URL in arrivo e in uscita alla ricerca di minacce, potrebbe modificare gli URL di partecipazione alla riunione e rendere la riunione non riconosciuto dal dispositivo Sale di Teams. Per assicurarsi che ciò non accada, è necessario aggiungere gli URL del servizio riunioni di terze parti all'elenco Collegamenti sicuri ATP "non riscrivere" o all'elenco delle eccezioni per la riscrittura degli URL di terze parti.

Per aggiungere URL del servizio per riunioni di terze parti all'elenco Collegamenti sicuri ATP "non riscrivere", seguire la procedura descritta in Configurare un elenco personalizzato di URL da non riscrivere mediante Collegamenti sicuri [ATP.](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-a-custom-do-not-rewrite-urls-list-with-atp?view=o365-worldwide) Se si usa una soluzione di terze parti, vedere le istruzioni per la soluzione in modo da aggiungere gli URL al relativo elenco di eccezioni per la riscrittura degli URL.

Ecco alcune voci di esempio che potrebbe essere necessario aggiungere all'elenco Collegamenti sicuri ATP "non riscrivere" o all'elenco di eccezioni per la riscrittura di URL di terze parti:

- **Cisco WebEx**`*.webex.com*`
- **Zoom** `*.zoom.us*` `*.zoom.com*` , , `*.zoomgov.com*`

Per un elenco completo degli URL da aggiungere all'elenco collegamenti sicuri ATP "non riscrivere" o all'elenco delle eccezioni per la riscrittura di URL di terze parti, contattare il provider di servizi per riunioni di terze parti da cui si vogliono accettare gli inviti alle riunioni. 

> [!CAUTION]
> Aggiungere solo gli URL attendibili all'elenco Collegamenti sicuri ATP "non riscrivere" o all'elenco di eccezioni per url di terze parti.

## <a name="step-3-enable-third-party-meetings-on-device"></a>Passaggio 3: Abilitare le riunioni di terze parti sul dispositivo

L'ultimo passaggio da eseguire è consentire a ogni dispositivo di Teams Room di partecipare a riunioni di terze parti. Per partecipare alle riunioni di terze parti è necessario un nome utente e un indirizzo di posta elettronica. Se il nome utente e l'indirizzo di posta elettronica da usare sono diversi dalla cassetta postale sala del dispositivo, è necessario aggiungerli al dispositivo. A questo scopo, usare le impostazioni del dispositivo o il file di configurazione XML.

### <a name="use-device-settings"></a>Usare le impostazioni del dispositivo

Per configurare il dispositivo Sale di Teams usando il touchscreen, eseguire le operazioni seguenti:

1. Nel dispositivo Microsoft Teams Rooms selezionare **Altro...**.
2. Selezionare **Impostazioni,** quindi immettere il nome utente e la password di amministratore del dispositivo.
3. Passare alla **scheda Riunioni** e selezionare **Cisco WebEx,** **Zoom** o entrambi.
4. Se si vuole partecipare a riunioni con il nome utente e l'indirizzo di posta elettronica associato alla cassetta postale della sala, selezionare Partecipa con le **informazioni sulla sala.**
5. Se si vuole partecipare alle riunioni con un  nome utente e un indirizzo di posta elettronica alternativi, selezionare Partecipa con informazioni personalizzate e immettere il nome utente e l'indirizzo di posta elettronica da usare.
6. Selezionare **Salva e esci.** Il dispositivo verrà riavviato.

### <a name="use-the-skypesettingsxml-configuration-file"></a>Usare il file SkypeSettings.xml di configurazione

Le impostazioni seguenti possono essere aggiunte al `SkypeSettings.xml` file disponibile in `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` . Per altre informazioni sul file, vedere Gestire le impostazioni della console di `SkypeSettings.xml` Microsoft Teams Room in remoto con un file di configurazione [XML.](xml-config-file.md)

Per abilitare le riunioni Cisco WebEx, impostare `WebExMeetingsEnabled` l'elemento XML **su True,** come indicato di seguito.

```xml
<WebExMeetingsEnabled>True</WebExMeetingsEnabled>
```

Per abilitare le riunioni con zoom, impostare `ZoomMeetingsEnabled` l'elemento XML su **True,** come indicato di seguito.

```xml
<ZoomMeetingsEnabled>True</ZoomMeetingsEnabled>
```

Se si desidera, è possibile specificare un nome utente e un indirizzo di posta elettronica personalizzati per partecipare a riunioni di terze parti usando gli elementi XML seguenti. Se i valori specificati non sono validi, il dispositivo Teams Rooms userà per impostazione predefinita il nome utente e l'indirizzo di posta elettronica della cassetta postale della sala.

```xml
<UseCustomInfoForThirdPartyMeetings>true</UseCustomInfoForThirdPartyMeetings>

<CustomDisplayNameForThirdPartyMeetings>guestname</CustomDisplayNameForThirdPartyMeetings>

<CustomDisplayEmailForThirdPartyMeetings>guest@contoso.com</CustomDisplayEmailForThirdPartyMeetings>
```

> [!NOTE]
> Per partecipare alla riunione Cisco WebEx da un dispositivo Teams Rooms, la riunione Cisco deve essere ospitata con L'applicazione Web Cisco WebEx versione WBS 40.7 o successiva.

