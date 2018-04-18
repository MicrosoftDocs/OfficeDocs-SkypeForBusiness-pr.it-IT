---
title: Distribuzione dei telefoni per Skype for Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
ms.assetid: faa17eb3-7483-4984-87f2-815d981b68ae
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
- Strat_SB_PSTN
description: Informazioni sulle procedure di distribuzione per ottenere il firmware corretto, aggiornare, se necessario, assegnare licenze e configurare le impostazioni per Skype per i telefoni online Business
ms.openlocfilehash: 2e1ee62dc2cd16a8aeec9b1eb744e4ca3f0155eb
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2018
---
# <a name="deploying-skype-for-business-online-phones"></a>Distribuzione dei telefoni per Skype for Business Online

[] Questa guida ti aiuta nella distribuzione dei telefoni IP per Skype for Business Online.
  
In tutti i tipi di aziende, con un numero di telefono consente agli utenti di effettuare e ricevono chiamate vocali ed è un requisito importante eseguire business. Gli utenti che dispongono di numeri di telefono saranno in grado di effettuare chiamate vocali in tutti i Skype per i dispositivi Business inclusi telefoni IP, PC e dispositivi mobili. È possibile ottenere ulteriori informazioni Skype per i telefoni IP Business leggendo [telefoni Getting Skype Business online](getting-phones-for-skype-for-business-online.md).
  
## <a name="deployment-steps-for-ip-phones"></a>Fasi della distribuzione di telefoni IP

### <a name="step-1---download-the-manufacturers-administrator-guides-and-phone-manuals"></a>Fase 1 - Scarica le guide per l'amministratore e i manuali del telefono del produttore

Prima di iniziare, è una buona idea quella di scaricare le guide per l'amministratore e i manuali d'uso del telefono del produttore.
  
- Per i telefoni Polycom, vedere [Polycom Deployment Guide] ((http://www.polycom.com/voice-conferencing-solutions/desktop-ip-phones.html).
    
- Per i telefoni Yealink, vedere [Skype Yealink for Business HD SIP telefoni Solution](http://www.yealink.com/products_top_2.html).
    
- Per i telefoni AudioCodes, consulta la [Guida alla gestione del provisioning Audiocodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions).
    
### <a name="step-2---make-sure-youre-purchasing-or-migrating-a-skype-for-business-supported-ip-phone-and-firmware"></a>Fase 2 - Assicurati di stare acquistando o migrando un telefono IP e firmware supportati da Skype for Business.

Un telefono e firmware supportati da Skype for Business Online sono compatibili anche con Skype for Business Server, ma non è sempre vero il contrario. Per verificare che si desidera acquistare o il provisioning di un telefono supportato e firmware, vedere [Getting telefoni Skype Business online](getting-phones-for-skype-for-business-online.md).
  
### <a name="step-3---checking-that-the-right-firmware-is-installed-and-update-the-firmware-if-required"></a>Fase 3 - Verifica che sia installato il firmware giusto e aggiorna il firmware, se necessario

Controllare la versione del firmware per i telefoni. Per:
  
- **Polycom VVX phones**, go to **Settings** > **Status** > **Platform** > **Application** > **Main**.
    
- i **telefoni Yealink**, accedi a **Status** (Stato) sulla schermata principale del telefono.
    
- **AudioCodes phones**, go to **Menu** > **Device Status** > **Firmware version** from the start screen.
    
    > [!NOTE]
    > Per l'accesso remoto per dettagli numero di telefono, fare riferimento alle guide di amministrazione dal produttore. Per le guide per gli utenti e i manuali phone, vedere i collegamenti di sopra. 
  
- I **telefoni Lync Phone Edition (LPE)**, accedi a **Menu** > **System Information** (Informazioni sul sistema) dalla schermata iniziale.
    
### <a name="step-4---device-update-considerations"></a>Fase 4 - Considerazioni sull'aggiornamento del dispositivo

> [!NOTE]
> Polycom firmware prima 5.5.1.X hanno un meccanismo di blocco del dispositivo specifiche del produttore viene sostituito con un Skype per l'implementazione di Business "Blocco telefono." L'aggiornamento di un telefono da 5.4.X.X in cui è stata impostata con "Blocco dispositivo" a 5.5.1.X con "Blocco telefono" non eredita il codice PIN da "Dispositivi-Lock", che è possibile lasciare il telefono non protetto. Gli utenti che hanno attivato "Blocco dispositivo" necessario abilitare il parametro profilo dispositivo Polycom seguente per fornire agli utenti il controllo del tempo di aggiornamento (lync.deviceUpdate.popUpSK.enabled=1). 
  
Gli upgrade del firmware sono gestiti dal servizio Skype for Business Service. Ogni firmware del telefono certificato Skype for Business viene caricato sul server Skype for Business Update e gli aggiornamenti dispositivo sono attivati su tutti i telefoni per impostazione predefinita. A seconda del tempo di inattività sul telefono e degli intervalli di polling, i telefoni scaricano e installano automaticamente l'ultima build certificata. È possibile disabilitare le impostazioni di aggiornamento dispositivo utilizzando il cmdlet [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) e l'impostazione del parametro _EnableDeviceUpdate_ `false`.
  
![Deploying phones.](../../images/be727622-1924-439f-96ca-89230739db9e.png)
  
Quando un nuovo firmware è disponibile ed è pronto per scaricare e installare, il telefono provvederà a darne comunicazione all'utente. Telefoni Polycom verranno notificare all'utente e fornire loro un'opzione di **aggiornamento** o **rimanda**.
  
![Deploying phones.](../../images/50956fa0-da0c-4085-9bb5-4a2e99aecebb.png)
  
Per un telefono Polycom, è possibile aggiornare il firmware del telefono selezionando **SwUpdate**.
  
![Deploying phones.](../../images/376c1998-6ce6-44b6-a84d-ae7d96b1c307.png)
  
Puoi anche scegliere di gestire gli aggiornamenti del firmware utilizzando un sistema di provisioning partner. Per la gestione del sistema di provisioning partner, compresa la personalizzazione avanzata del telefono, consulta le guide per l'amministratore del produttore.
  
> [!CAUTION]
> Assicurati di avere un'unica autorità di aggiornamento dispositivi (aggiornamento del dispositivo in banda o server di provisioning di terze parti) per evitare loop di aggiornamento. 
  
### <a name="step-5---configuration-and-infrastructure-phone-settings"></a>Passaggio 5 - e configurazione dell'infrastruttura telefonica

Puoi impostare le opzioni e i criteri del telefono più comunemente utilizzati che utilizzano i cmdlet di Windows PowerShell per la gestione in banda di Skype for Business. Consulta [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) per i dettagli di questi parametri e impostazioni.
  
Per la pianificazione dell'infrastruttura di rete, vedere [Skype Operations Framework](https://www.skypeoperationsframework.com/).
  
### <a name="step-6---preparing-for-users-to-sign-in"></a>Passaggio 6 - preparazione agli utenti di effettuare l'accesso

Per consentire agli utenti di accedere a un Skype per il telefono aziendale Online correttamente ed effettuare chiamate, è necessario assicurarsi che gli utenti vengono assegnati le licenze corrette. Come minimo, è necessario assegnare una licenza di sistema telefonico e un piano di chiamata. Per ulteriori informazioni, è possibile vedere [Skype di licenza di componente aggiuntivo Business e i team di Microsoft](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md) e [Assegnare Skype per le licenze aziendali e team di Microsoft](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).
  
È possibile trovare ulteriori informazioni sui piani di chiamata leggendo [che cosa sono i piani di chiamata in Office 365?](../../what-are-calling-plans-in-office-365/what-are-calling-plans-in-office-365.md)
  
- Le **opzioni di accesso** disponibili per gli utenti online son le seguenti.
    
  - Verrà visualizzato dagli utenti ai telefoni **Polycom VVX 5XX/6XX** :
    
     ![Deploying phones.](../../images/8a1ffb33-8a63-4242-bb76-d5fafb6a6472.png)
  
  - Verrà visualizzato dagli utenti ai telefoni **Yealink T48G/T46G** :
    
     ![Yealink phones logon.](../../images/2a2892ae-850d-4781-8be0-4ffb8af068c9.png)
  
    Per ulteriori informazioni sulle opzioni di accesso supportate dal produttore, vedere [Getting telefoni Skype Business online](getting-phones-for-skype-for-business-online.md).
    
- **ID utente** Utilizzando la tastiera del telefono o la tastiera a schermo (se disponibile), gli utenti possono utilizzare il nome utente e la password della propria organizzazione per accedere al telefono. Ad esempio, possono utilizzare il formato UPN come *amosm@contoso.com*  per il nome utente.
    
     ![Deploying phones.](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
    > [!NOTE]
    > L'autenticazione PIN non è supportata per Skype for Business online per i telefoni IP LPE e Partner. 
  
- **Utilizzo di un PC** Se Better Together su software Ethernet (BToE) è installato nel computer dell'utente è abilitato, gli utenti possono accedere ai propri telefoni utilizzando la finestra di autenticazione nella loro Skype Windows per applicazioni aziendali. Per altre informazioni, vedere [passaggio 7 (facoltativo) - se si dispone di abbinamento di dispositivi e Better Together over Ethernet (BToE)](deploying-skype-for-business-online-phones.md#BK_BTOE) .
    
    > [!NOTE]
    > Gli utenti devono utilizzare il nome utente e la password della propria organizzazione per accedere al telefono. Ad esempio, possono utilizzare il formato UPN come  *amosm@contoso.com*  per il nome utente.
  
     ![Deploying phones.](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
- **Utilizzando un accesso Web**: si tratta di un nuovo modo per gli utenti in linea per l'autenticazione utilizzando un web browser standard. Agli utenti verranno fornito con una serie di istruzioni da seguire quando si utilizza un browser per l'accesso.
    
  - Verrà visualizzato dagli utenti ai telefoni **Polycom VVX 5XX/6XX** :
    
     ![Deploying phones.](../../images/ba0df923-a6e5-4a9b-b40b-b03ca188e814.png)
  
  - Verrà visualizzato dagli utenti ai telefoni **Yealink T48G/T46G** :
    
     ![Yealink phone logon.](../../images/86551cc3-533a-4694-9683-bad907c9ad5a.png)
  
    Il codice generato scade dopo 15 minuti. Quando scade, sarà necessario all'utente di scegliere **Riprova** o **OK** per generare un nuovo codice, a seconda del telefono.
    
  - Verrà visualizzato dagli utenti ai telefoni **Polycom VVX 5XX/6XX** :
    
     ![PIN code expired.](../../images/b5d27037-aa26-4054-be95-d5a6c293d08c.png)
  
  - Verrà visualizzato dagli utenti ai telefoni **Yealink T48G/T46G** :
    
     ![Yealink phones logon.](../../images/3a4462ac-0c59-409e-a3bb-1451cdcc8676.png)
  
    Utilizzando un browser, accedi all'indirizzo visualizzato sul telefono e inserisci il tuo nome utente Skype for Business.
    
     ![Deploying phones.](../../images/7c540b85-dc37-4ce7-a077-9e3454a0efd0.png)
  
    Immetti il codice mostrato sul telefono.
    
     ![Deploying phones.](../../images/d6b88016-35d2-41d1-a0da-81fef34521d4.png)
  
    Verificare che il sito positivo "[nome del produttore del telefono] **Skype per telefono ufficio Certified**" e fare clic su **Continua**.
    
     ![Deploying phones.](../../images/a8252b37-4ff5-4ece-9e2a-3e05bf928299.png)
  
    Fai clic sulle credenziali dell'utente o fai clic su **Usa un altro account**:
    
     ![Deploying phones.](../../images/8415028b-7924-4747-b639-052d9b0b961e.png)
  
    Quando viene visualizzata la pagina seguente, è consigliabile chiudere il browser.
    
     ![Deploying phones.](../../images/1a873201-52fc-4a63-b7b5-e82bbd031fd2.png)
  
    > [!NOTE]
    > I telefoni LPE per Skype for Business online supportano l'accesso solo attraverso tethering USB. 
  
- **Distribuzioni supportate** La tabella seguente mostra i tipi di autenticazione supportati per i modelli di distribuzione attualmente supportati tra cui integrazione Exchange, autenticazione moderna con autenticazione a più fattori (MFA) e Skype for Business online e locale.
    
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Skype for Business** <br/> |**Exchange** <br/> |**Metodo di accesso telefono** <br/> |**Skype per l'accesso Business** <br/> |**Accesso Exchange con autorizzazione moderna e MFA disattivate** <br/> |**Accesso Exchange con autorizzazione moderna e MFA attivate** <br/> |
|Online  <br/> |Online  <br/> |Accesso Web  <br/> |Sì  <br/> |Sì  <br/> |Sì  <br/> |
|Online  <br/> |Online  <br/> |Nome utente/password  <br/> |Sì  <br/> |Sì  <br/> |No  <br/> |
|Online  <br/> |Locale  <br/> |Accesso Web  <br/> |Sì  <br/> |No  <br/> |No  <br/> |
|Online  <br/> |Locale  <br/> |Nome utente/password  <br/> |Sì  <br/> |Sì  <br/> |No  <br/> |
|Locale  <br/> |Online/locale  <br/> |Autenticazione basata su PIN  <br/> |Sì  <br/> |No  <br/> |No  <br/> |
|Locale  <br/> |Online/locale  <br/> |Nome utente/password  <br/> |Sì  <br/> |Sì  <br/> |N/A  <br/> |
|Locale  <br/> |Online/locale  <br/> |Accesso via PC (BTOE)  <br/> |Sì  <br/> |Sì  <br/> |N/A  <br/> |
   
- **Funzionalità del telefono** Il set di caratteristiche può variare leggermente a seconda del partner telefono IP. Imposta per la funzionalità completa e per ulteriori informazioni sulle funzionalità per ogni produttore del telefono, vedere [Getting telefoni Skype Business online](getting-phones-for-skype-for-business-online.md).
    
- **Phone-Lock** è una funzionalità di recente introduzione nei telefoni certificati Skype for Business che permette di proteggere un telefono. Se attivata, gli utenti verranno richiesto di creare un PIN dopo un'autenticazione eseguita correttamente. Una volta creato il PIN, il telefono si blocca quando scade un periodo di inattività definito, quando l'utente blocca manualmente il telefono o quando sincronizza il proprio Phone-Lock con il blocco su PC utilizzando l'accoppiamento del telefono. Se blocco telefono viene immesso il PIN errato più volte, il telefono verrà disconnesso l'utente o richiedono il codice dell'amministratore di sbloccare il telefono, ma questa variano a seconda del partner telefono. Il PIN dell'utente deve essere compresa tra 6 e 15 cifre.
    
    È possibile disattivare Blocco telefono per l'organizzazione (in cui è abilitata per impostazione predefinita), modificare il timeout di inattività e scegliere se gli utenti possono effettuare chiamate telefoniche mentre sono bloccate o non tramite le impostazioni inband. Per ulteriori informazioni su queste impostazioni, vedere [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) .
    
## <a name="step-7-optional---if-you-have-device-pairing-and-better-together-over-ethernet-btoe"></a>Fase 7 (opzionale) - Con accoppiamento dispositivo e Better Together over Ethernet (BToE)
<a name="BK_BTOE"> </a>

BToE è un telefono paining meccanismo per i telefoni IP Partner che è possibile associare telefono di un utente con le Skype Windows per applicazioni aziendali. BToE consente agli utenti di:
  
- Accedere al proprio telefono IP con loro Skype per l'app desktop Business (utilizzando un PC)
    
- Sincronizzare blocco telefono con blocco PC
    
- Fare clic per chiamare
    
BToE può essere configurato per operare in due modalità: *automatico* (impostazione predefinita) e *manuale* . Può anche essere abilitato (impostazione predefinita)/disabilitato per gli utenti che utilizzano le impostazioni in banda di Skype for Business. In modalità *Manuale*  , gli utenti dovranno eseguire un ulteriore passaggio per accoppiare il telefono alla app su Windows.
  
 **Per distribuire BToE agli utenti**
  
1. Collegare il PC al telefono utilizzando la porta del PC.
    
     ![Deploying phones.](../../images/e21d76c7-867c-4fe6-95c6-fc40c608ed0c.png)
  
2. Scaricare e installare l'ultima versione del software BToE dal sito web del produttore dai link qui sotto. Per una migliore esperienza utente, è possibile distribuire e installare il software BToE utilizzando una soluzione di distribuzione di amministrazione come System Center Configuration Manager (SCCM). Per informazioni sull'utilizzo di SCCM, consulta [Pacchetti e programmi in System Center Configuration Manager](https://docs.microsoft.com/en-us/sccm/apps/deploy-use/packages-and-programs).
    
  - [Sito di Download di Polycom BToE Software](http://www.polycom.com/voice-conferencing-solutions/microsoft-phones.html)
    
  - [Download software BToE Yealink](http://www.yealink.com/products_list_10.html)
    
  - [Download software BToE AudioCodes](https://www.audiocodes.com/solutions-products/solutions/skype-for-business-microsoft-teams/skype-for-business-online)
    
3. L'impostazione del server per BToE è impostata su **abilitato** e **la modalità automatica** per impostazione predefinita. Per modificare le impostazioni, vedere [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx).
    
> [!NOTE]
> BToE non è attualmente supportato su piattaforme Mac e VDI. 
  
## <a name="related-topics"></a>Argomenti correlati
[Ottenere numeri di servizio per Skype for Business e Microsoft Teams](../../what-is-phone-system-in-office-365/getting-service-phone-numbers.md)

[Ecco cosa offre il Sistema telefonico in Office 365](../../what-is-phone-system-in-office-365/here-s-what-you-get-with-phone-system.md)

[Disponibilità di Audioconferenza e Piani per chiamate per paese e area geografica](../../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

  
 
