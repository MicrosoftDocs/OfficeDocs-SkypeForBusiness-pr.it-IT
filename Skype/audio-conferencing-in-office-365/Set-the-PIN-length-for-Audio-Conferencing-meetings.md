---
title: Impostare la lunghezza del PIN per le riunioni di conferenze Audio
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: b86d31c6-1543-478f-b8c6-4b71e708403a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: Ulteriori parametri per la lunghezza e i requisiti di un PIN e informazioni su come impostare il periodo per le riunioni in Skype per le aziende.
ms.openlocfilehash: 853a8ed74377dd76b38eab62b04fc75e3295df2d
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/15/2017
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings"></a>Impostare la lunghezza del PIN per le riunioni di conferenze Audio

Quando imposta audioconferenze con accesso esterno in per Skype per Business o Microsoft Teams, si otterrà un ponte per conferenze audio. Un ponte per conferenze può contenere uno o più numeri di telefono. Si imposta il numero di telefono verrà inclusa in inviti riunione per Skype per le applicazioni aziendali e Teams Microsoft.
  
Ponte per conferenze audio risponde a una chiamata a coloro che si collegano a una riunione utilizzando un telefono. Vengono fornite risposte al chiamante di istruzioni vocali da un operatore automatico e quindi, a seconda delle impostazioni, può riprodurre le notifiche e chiedere ai chiamanti di registrare il proprio nome. **Impostazioni bridge Microsoft** consentono di modificare le impostazioni per le notifiche di riunione e la riunione partecipare esperienza e impostare la lunghezza del PIN che vengono utilizzati per gli organizzatori delle riunioni. Per avviare riunioni se è Impossibile partecipare alla riunione utilizzando il Skype per applicazioni aziendali o Microsoft Teams, gli organizzatori delle riunioni eseguire PIN.
  
## <a name="setting-the-pin-length"></a>Impostazione della lunghezza PIN

1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.
    
3. Nella **Skype per interfaccia di amministrazione di Business**, nel riquadro di spostamento sinistro, passare a **conferenze Audio** > **Impostazioni bridge di Microsoft**.
    
4. In **sicurezza** > **lunghezza del PIN**, selezionare il numero di cifre che si desidera utilizzare per il PIN e quindi fare clic su **Salva**.
    
> [!NOTE]
> Un PIN è diverso da un ID conferenza. ID conferenza vengono utilizzati per i chiamanti quando partecipano a riunione. Vengono utilizzati per identificare la riunione. Il PIN viene utilizzato per autenticare un chiamante organizzatore della riunione. 
  
## <a name="want-to-know-more-about-pin-settings"></a>Fonti di informazioni sulle impostazioni del PIN

- PIN può essere da 4 a 12 cifre. il valore predefinito è 5. I numeri vengono utilizzati solo quando si crea PIN. Lettere e caratteri speciali non vengono utilizzati.
    
- Un PIN è solo necessario per l'organizzatore della riunione quando Skype per utenti Business o Teams Microsoft non ha già avviato la riunione. Se tutti gli utenti è accedono alla riunione, il PIN è obbligatorio per l'organizzatore della riunione avviare la riunione.
    
- Impostazioni di protezione PIN vengono applicate a tutti i numeri di telefono associati a un ponte Microsoft. Essi verranno applicate a tutte le riunioni che utilizzano i numeri di telefono associati a un ponte specificato. 
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Vuoi sapere come gestire queste operazioni con Windows PowerShell?

- Per risparmiare tempo o automatizzare questa operazione, è possibile utilizzare il cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757) .
    
- Per impostare il numero di cifre in Aggiungi a 8:`Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`
    
- Windows PowerShell è incentrato sulla gestione degli utenti e quali utenti sono consentiti o non è autorizzati a eseguire. Con Windows PowerShell, è possibile gestire Office 365 con un singolo punto di amministrazione che consente di semplificare le attività quotidiane quando si dispone di più attività da eseguire. Per iniziare a usare Windows PowerShell, vedere i seguenti argomenti:
    
  - [Perché è necessario utilizzare Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Modi migliori per gestire Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell offre numerosi vantaggi in velocità, la semplicità e produttività rispetto solo tramite l'interfaccia di amministrazione di Office 365, ad esempio se si sta creando le modifiche alle impostazioni per molti utenti contemporaneamente. Informazioni su queste vantaggiose caratteristiche negli argomenti seguenti: 
    
  - [Introduzione a Windows Powershell e Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Uso di Windows PowerShell per gestire Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
    [Uso di Windows PowerShell per gestire Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Il modulo Windows PowerShell per Skype for Business online consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo nei computer a 64 bit, può essere scaricato dall'Area download Microsoft nel [modulo Windows PowerShell per Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="see-also"></a>Le differenze nella nostra funzionalità di chiamata ai servizi di emergenza includono quanto segue: (i) Skype for Business potrebbe non conoscere la posizione effettiva di un chiamante ai servizi di emergenza, il che potrebbe comportare un instradamento della chiamata ai servizi di emergenza a un call center dei servizi di emergenza errato e/o l'invio dei servizi di emergenza a una località errata; (ii) se il dispositivo dell'utente non riceve l'alimentazione, sta sperimentando un'interruzione dell'alimentazione, o per qualsiasi motivo, non è in grado di accedere a Internet, l'utente non potrà effettuare la chiamata ai servizi di emergenza tramite i Piani per chiamate di Office 365; e (iii) sebbene i Piani per chiamate di Office 365 possano essere usati ovunque nel mondo laddove sia disponibile una connessione a Internet, gli utenti non dovrebbero chiamare i servizi di emergenza da una località al di fuori del proprio paese/regione poiché la chiamata non verrà probabilmente instradata al call center appropriato di tale paese/area geografica.

[Configurare le audioconferenze per Skype for Business e Microsoft Teams](set-up-audio-conferencing.md)

