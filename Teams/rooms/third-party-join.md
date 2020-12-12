---
title: Abilitare i dispositivi di teams Rooms per partecipare a riunioni di terze parti
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
description: Questo articolo illustra come configurare i dispositivi dell'organizzazione e dei team Rooms per supportare la partecipazione a una riunione di terze parti a Cisco WebEx e zoom.
ms.openlocfilehash: 8079b6fc231bf30a654e2513af55a806433eb83f
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662361"
---
# <a name="enable-teams-room-devices-to-join-third-party-meetings"></a>Consentire ai dispositivi della sala team di partecipare a riunioni di terze parti

I dispositivi Microsoft teams Rooms supportano un'esperienza One-Touch per partecipare a riunioni online di terze parti. Quando è abilitata, è possibile usare un dispositivo teams Rooms per partecipare a riunioni ospitate in Cisco WebEx e zoom<sup>1</sup> con la stessa facilità con cui è possibile partecipare a riunioni ospitate in Microsoft teams.

Prima di poter partecipare a riunioni di terze parti da un dispositivo di teams rooms, è necessario eseguire le operazioni seguenti:

1. Configurare la cassetta postale della sala di Exchange Online del dispositivo teams Rooms per elaborare gli inviti per riunioni di terze parti
2. Verificare che l'organizzazione non disponga di criteri che impediscano la connessione a servizi di riunione di terze parti
3. Configurare i dispositivi di teams Rooms per consentire riunioni di terze parti

Le sezioni seguenti illustrano come eseguire ognuno di questi passaggi.

## <a name="step-1-allow-calendar-invite-processing-for-third-party-meetings"></a>Passaggio 1: consentire l'elaborazione dell'invito del calendario per le riunioni di terze parti

La prima cosa da fare per abilitare un'esperienza di join One-Touch da un dispositivo di Team Rooms è impostare le regole di elaborazione del calendario per la cassetta postale della sala di Exchange Online del dispositivo. La cassetta postale della sala deve consentire riunioni esterne e tenere il corpo del messaggio e l'oggetto in modo che possa vedere l'URL necessario per partecipare alla riunione di terze parti. Per impostare le opzioni delle cassette postali della sala usando il cmdlet [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/set-calendarprocessing?view=exchange-ps.) , eseguire le operazioni seguenti:

1. Connettersi a PowerShell di Exchange Online. Per altre informazioni, vedere [connettersi a PowerShell di Exchange Online con l'autenticazione di base](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps) o [connettersi a PowerShell di Exchange Online con l'autenticazione](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell?view=exchange-ps)a più fattori, a seconda del metodo di autenticazione.

2. Ottenere il nome dell'entità utente (UPN) della cassetta postale della sala se non lo si conosce eseguendo il comando seguente:

    ```powershell
    Get-Mailbox | Where {$_.RoomMailboxAccountEnabled -eq $True} | Format-Table Name, UserPrincipalName
    ```
3. Trovare il nome della cassetta postale della sala associata al dispositivo teams Rooms e prendere nota del relativo UPN

4. Dopo aver trovato l'UPN della cassetta postale della sala, eseguire il comando seguente. Sostituire `<UserPrincipalName>` con l'UPN della cassetta postale della sala:

    ```powershell
    Set-CalendarProcessing <UserPrincipalName> -ProcessExternalMeetingMessages $True -DeleteComments $False -DeleteSubject $False
    ```

Altre informazioni su [PowerShell di Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell?view=exchange-ps).

## <a name="step-2-configure-office-365-threat-protection-and-link-rewrite"></a>Passaggio 2: configurare la protezione delle minacce di Office 365 e la riscrittura dei collegamenti

Per abilitare l'esperienza di join One-Touch, le informazioni sul collegamento alla riunione di partecipazione dalla riunione di terze parti devono essere presenti e leggibili nell'invito alla riunione. Se l'organizzazione usa la caratteristica [collegamenti attendibili di Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links) o se si usa una soluzione di terze parti che analizza tutti gli URL in entrata e in uscita per le minacce, può modificare gli URL di join della riunione e rendere la riunione irriconoscibile dal dispositivo teams rooms. Per verificare che non si verifichi questo problema, è necessario aggiungere gli URL del servizio di riunione di terze parti all'elenco collegamenti sicuri ATP "non riscrivere" o all'elenco di eccezioni di riscrittura URL di terze parti.

Per aggiungere URL del servizio di riunione di terze parti all'elenco collegamenti sicuri ATP "non riscrivere", seguire i passaggi descritti in [configurare un elenco di URL non riscrivibile personalizzato usando collegamenti sicuri ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-a-custom-do-not-rewrite-urls-list-with-atp?view=o365-worldwide). Se si usa una soluzione di terze parti, vedere le istruzioni per la soluzione per aggiungere URL all'elenco di eccezioni di riscrittura URL.

Ecco alcuni esempi di voci che potrebbe essere necessario aggiungere ai collegamenti sicuri ATP "non riscrivere" o elenco di eccezioni di riscrittura URL di terze parti:

- **Cisco WebEx**`*.webex.com*`
- **Zoom** `*.zoom.us*` , `*.zoom.com*``*.zoomgov.com*`

Per un elenco completo degli URL da aggiungere ai collegamenti sicuri ATP "non riscrivere", elenco di eccezioni di riscrittura URL di terze parti, contattare il provider di servizi di terze parti a cui si vogliono accettare gli inviti alla riunione. 

> [!CAUTION]
> Aggiungere solo gli URL attendibili per i collegamenti sicuri ATP "non riscrivere" o elenco di eccezioni di riscrittura URL di terze parti.

## <a name="step-3-enable-third-party-meetings-on-device"></a>Passaggio 3: abilitare riunioni di terze parti sul dispositivo

L'ultimo passaggio da eseguire è consentire a ogni dispositivo sale team di partecipare a riunioni di terze parti. Le riunioni di terze parti richiedono un nome utente e un indirizzo di posta elettronica per partecipare. Se il nome utente e l'indirizzo di posta elettronica che è necessario usare sono diversi dalla cassetta postale della sala del dispositivo, è necessario aggiungerli al dispositivo. Questa operazione può essere eseguita nelle impostazioni del dispositivo o nel file di configurazione XML.

### <a name="use-device-settings"></a>Usare le impostazioni del dispositivo

Per configurare il dispositivo teams Rooms usando il touchscreen, eseguire le operazioni seguenti:

1. Nel dispositivo Microsoft teams Rooms selezionare **altro...**
2. Selezionare **Impostazioni** e quindi immettere il nome utente e la password dell'amministratore del dispositivo
3. Passare alla scheda **riunioni** e selezionare **Cisco WebEx**, **Zoom**<sup>1</sup>o entrambi
4. Per partecipare alle riunioni con il nome utente e l'indirizzo di posta elettronica associato alla cassetta postale della sala, selezionare **partecipa con info sala**
5. Per partecipare alle riunioni con un nome utente e un indirizzo di posta elettronica alternativi, selezionare **partecipa con info personalizzate** e immettere il nome utente e l'indirizzo di posta elettronica che si vuole usare
6. Selezionare **Salva ed esci**. Il dispositivo verrà riavviato.

### <a name="use-the-skypesettingsxml-configuration-file"></a>Usare il file di configurazione SkypeSettings.xml

Le impostazioni seguenti possono essere aggiunte al `SkypeSettings.xml` file che si trova in `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` . Per altre informazioni sul `SkypeSettings.xml` file, vedere [gestire le impostazioni della console Microsoft teams rooms in remoto con un file di configurazione XML](xml-config-file.md).

Per abilitare le riunioni Cisco WebEx, imposta l' `WebExMeetingsEnabled` elemento XML su **true**, come indicato di seguito.

```xml
<WebExMeetingsEnabled>True</WebExMeetingsEnabled>
```

Per abilitare le riunioni zoom <sup>1</sup> , imposta l' `ZoomMeetingsEnabled` elemento XML su **true**, come indicato di seguito.

```xml
<ZoomMeetingsEnabled>True</ZoomMeetingsEnabled>
```

Puoi facoltativamente specificare un nome utente e un indirizzo di posta elettronica personalizzati per partecipare a riunioni di terze parti usando gli elementi XML seguenti. Se i valori forniti non sono validi, il dispositivo teams Rooms utilizzerà automaticamente il nome utente e l'indirizzo di posta elettronica della cassetta postale della sala.

```xml
<UseCustomInfoForThirdPartyMeetings>true</UseCustomInfoForThirdPartyMeetings>

<CustomDisplayNameForThirdPartyMeetings>guestname</CustomDisplayNameForThirdPartyMeetings>

<CustomDisplayEmailForThirdPartyMeetings>guest@contoso.com</CustomDisplayEmailForThirdPartyMeetings>
```

> [!NOTE]
> Per partecipare a una riunione Cisco WebEx da un dispositivo di teams rooms, la riunione Cisco deve essere ospitata usando la versione WBS 40,7 o successiva di Cisco WebEx Web Application.

<sup>1</sup> la partecipazione alle riunioni zoom è attualmente disponibile solo per selezionare i clienti di Microsoft teams Rooms tramite il programma di accesso alla tecnologia (TAP).
