---
title: Consentire ai dispositivi di Teams Rooms di partecipare a riunioni di terze parti
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
description: Questo articolo illustra come configurare l'organizzazione e i dispositivi di Teams Rooms per supportare la partecipazione a riunioni di terze parti a Cisco WebEx e Zoom.
ms.openlocfilehash: c8f6bda7680ccd3107c313c87001902e442518c9
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117374"
---
# <a name="enable-teams-room-devices-to-join-third-party-meetings"></a>Abilitare i dispositivi di Teams Room per partecipare a riunioni di terze parti

I dispositivi Microsoft Teams Rooms supportano un'esperienza con un solo tocco per partecipare a riunioni online di terze parti, detta anche partecipazione guest diretta. Se abilitata, è possibile usare un dispositivo Teams Rooms per partecipare a riunioni ospitate su Cisco WebEx e Zoom con la facilità con cui è possibile partecipare alle riunioni ospitate in Microsoft Teams.

Prima di poter partecipare a riunioni di terze parti da un dispositivo Teams Rooms, è necessario eseguire le operazioni seguenti:

1. Configurare la cassetta postale della chat room di Exchange Online del dispositivo Teams Rooms per elaborare gli inviti per riunioni di terze parti.
2. Assicurarsi che l'organizzazione non abbia criteri che impediscono la connessione a servizi di riunione di terze parti.
3. Configurare i dispositivi di Teams Rooms per consentire riunioni di terze parti.

Le sezioni seguenti illustrano come eseguire ognuno di questi passaggi.

## <a name="step-1-allow-calendar-invite-processing-for-third-party-meetings"></a>Passaggio 1: Consentire l'elaborazione degli inviti al calendario per le riunioni di terze parti

La prima cosa da fare per abilitare un'esperienza di partecipazione con un solo tocco da un dispositivo Team Rooms è impostare le regole di elaborazione del calendario per la cassetta postale sala di Exchange Online del dispositivo. La cassetta postale della sala deve consentire riunioni esterne e mantenere il corpo e l'oggetto del messaggio in modo che possa vedere l'URL necessario per partecipare alla riunione di terze parti. Per impostare queste opzioni della cassetta postale sala usando il cmdlet [Set-CalendarProcessing,](/powershell/module/exchange/set-calendarprocessing?view=exchange-ps.) eseguire le operazioni seguenti:

1. Connettersi a PowerShell di Exchange Online. Per altre informazioni, vedere Connettersi a [PowerShell di Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps) con l'autenticazione di base o Connettersi a [PowerShell di Exchange Online](/powershell/exchange/mfa-connect-to-exchange-online-powershell?view=exchange-ps)usando l'autenticazione a più fattori, a seconda del metodo di autenticazione.

2. Ottenere il nome dell'entità utente (UPN) della cassetta postale della chat room se non lo si conosce eseguendo il comando seguente:Get the User Principal Name (UPN) of the room mailbox if you don't know it by running the following command:

    ```powershell
    Get-Mailbox | Where {$_.RoomMailboxAccountEnabled -eq $True} | Format-Table Name, UserPrincipalName
    ```
    
3. Trovare il nome della cassetta postale della chat room associata al dispositivo Teams Rooms e prendere nota del relativo UPN.

4. Dopo aver trovato l'UPN della cassetta postale sala, eseguire il comando seguente. Sostituire `<UserPrincipalName>` con l'UPN della cassetta postale sala:

    ```powershell
    Set-CalendarProcessing <UserPrincipalName> -ProcessExternalMeetingMessages $True -DeleteComments $False -DeleteSubject $False
    ```

Altre informazioni su [PowerShell di Exchange Online.](/powershell/exchange/exchange-online-powershell?view=exchange-ps)

## <a name="step-2-configure-office-365-threat-protection-and-link-rewrite"></a>Passaggio 2: Configurare Office 365 Threat Protection e la riscrittura dei collegamenti

Per abilitare l'esperienza di partecipazione con un solo tocco, le informazioni sul collegamento di partecipazione alla riunione della riunione di terze parti devono essere presenti e leggibili nell'invito alla riunione. Se l'organizzazione usa la caratteristica Collegamenti sicuri di [Office 365 Advanced Threat Protection](/microsoft-365/security/office-365-security/atp-safe-links) o se si usa una soluzione di terze parti che analizza tutti gli URL in arrivo e in uscita alla ricerca di minacce, può modificare gli URL di partecipazione alla riunione e rendere la riunione irriconoscibile dal dispositivo Teams Rooms. Per assicurarsi che non accada, è necessario aggiungere gli URL del servizio riunioni di terze parti all'elenco collegamenti sicuri ATP "non riscrivere" o all'elenco di eccezioni di riscrittura URL di terze parti.

Per aggiungere URL del servizio riunioni di terze parti all'elenco Collegamenti sicuri ATP "non riscrivere", seguire la procedura descritta in Configurare un elenco personalizzato di URL non riscrivere usando Collegamenti sicuri [ATP.](/microsoft-365/security/office-365-security/set-up-a-custom-do-not-rewrite-urls-list-with-atp?view=o365-worldwide) Se si usa una soluzione di terze parti, vedere le istruzioni per tale soluzione per aggiungere URL al relativo elenco di eccezioni di riscrittura URL.

Ecco alcune voci di esempio che potrebbe essere necessario aggiungere all'elenco di eccezioni "non riscrivere" collegamenti sicuri ATP o url di terze parti:

- **Cisco WebEx**`*.webex.com*`
- **Zoom** `*.zoom.us*` , `*.zoom.com*` , `*.zoomgov.com*`

Per un elenco completo di URL da aggiungere all'elenco di eccezioni "non riscrivere" collegamenti sicuri ATP o all'elenco di eccezioni di riscrittura url di terze parti, contattare il provider di servizi di riunione di terze parti da cui si vogliono accettare gli inviti alle riunioni. 

> [!CAUTION]
> Aggiungere solo URL attendibili all'elenco di eccezioni di riscrivere i collegamenti sicuri ATP o a url di terze parti.

## <a name="step-3-enable-third-party-meetings-on-device"></a>Passaggio 3: Abilitare le riunioni di terze parti nel dispositivo

L'ultimo passaggio da eseguire è consentire a ogni dispositivo di Teams Rooms di partecipare a riunioni di terze parti. Per partecipare alle riunioni di terze parti è necessario un nome utente e un indirizzo di posta elettronica. Se il nome utente e l'indirizzo di posta elettronica da usare sono diversi dalla cassetta postale della sala del dispositivo, è necessario aggiungerli al dispositivo. È possibile eseguire questa operazione nelle impostazioni del dispositivo o nel file di configurazione XML.

### <a name="use-device-settings"></a>Usare le impostazioni del dispositivo

Per configurare il dispositivo Teams Rooms usando il touchscreen, eseguire le operazioni seguenti:

1. Nel dispositivo Microsoft Teams Rooms selezionare **Altro ...**.
2. Selezionare **Impostazioni** e quindi immettere il nome utente e la password dell'amministratore del dispositivo.
3. Passare alla scheda **Riunioni** e selezionare **Cisco WebEx**, **Zoom** o entrambi.
4. Se si vuole partecipare alle riunioni con il nome utente e l'indirizzo di posta elettronica associati alla cassetta postale della sala, selezionare **Partecipa con le informazioni sulla sala.**
5. Se si vuole partecipare alle riunioni con un  nome utente e un indirizzo di posta elettronica alternativi, selezionare Partecipa con informazioni personalizzate e immettere il nome utente e l'indirizzo di posta elettronica da usare.
6. Selezionare **Salva e esci.** Il dispositivo verrà riavviato.

### <a name="use-the-skypesettingsxml-configuration-file"></a>Usare il file SkypeSettings.xml file di configurazione

Le impostazioni seguenti possono essere aggiunte al `SkypeSettings.xml` file che si trova in `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` . Per altre informazioni sul file, vedere Gestire le impostazioni della console di `SkypeSettings.xml` Microsoft Teams Rooms in remoto con un file di configurazione [XML.](xml-config-file.md)

Per abilitare le riunioni Cisco WebEx, impostare `WebExMeetingsEnabled` l'elemento XML su **True**, come indicato di seguito.

```xml
<WebExMeetingsEnabled>True</WebExMeetingsEnabled>
```

Per abilitare le riunioni zoom, impostare `ZoomMeetingsEnabled` l'elemento XML su **True**, come indicato di seguito.

```xml
<ZoomMeetingsEnabled>True</ZoomMeetingsEnabled>
```

Facoltativamente, è possibile specificare un nome utente e un indirizzo di posta elettronica personalizzati per partecipare a riunioni di terze parti usando gli elementi XML seguenti. Se i valori specificati non sono validi, il dispositivo Teams Rooms userà per impostazione predefinita il nome utente e l'indirizzo di posta elettronica della cassetta postale della sala.

```xml
<UseCustomInfoForThirdPartyMeetings>true</UseCustomInfoForThirdPartyMeetings>

<CustomDisplayNameForThirdPartyMeetings>guestname</CustomDisplayNameForThirdPartyMeetings>

<CustomDisplayEmailForThirdPartyMeetings>guest@contoso.com</CustomDisplayEmailForThirdPartyMeetings>
```

> [!NOTE]
> Per partecipare a una riunione Cisco WebEx da un dispositivo Teams Rooms, la riunione Cisco deve essere ospitata con l'applicazione Web Cisco WebEx versione WBS 40.7 o successiva.