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
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Priority
f1keywords: None
ms.custom:
- Phone System
description: Informazioni sulle procedure di distribuzione per ottenere il firmware corretto, aggiornare, se necessario, assegnare licenze e configurare le impostazioni per telefoni per Skype for Business online
ms.openlocfilehash: 3b695f0198e5edb23a8746babb071742d7b7712f
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "23860460"
---
# <a name="deploying-skype-for-business-online-phones"></a>Distribuzione dei telefoni per Skype for Business online

[] Questa guida ti aiuta nella distribuzione dei telefoni IP per Skype for Business Online.
  
In ogni genere di azienda, un numero di telefono consente agli utenti di effettuare e ricevere chiamate vocali, ed è un requisito importante per condurre gli affari. Gli utenti che hanno numeri di telefono potranno effettuare chiamate vocali su tutti i dispositivi Skype for Business tra cui telefoni IP, PC e dispositivi mobili. Per saperne di più sui telefoni IP per Skype for Business, consulta [Ottenere telefoni per Skype for Business online](getting-phones-for-skype-for-business-online.md).
  
## <a name="deployment-steps-for-ip-phones"></a>Fasi della distribuzione di telefoni IP

### <a name="step-1---download-the-manufacturers-administrator-guides-and-phone-manuals"></a>Fase 1 - Scarica le guide per l'amministratore e i manuali del telefono del produttore

Prima di iniziare, è una buona idea quella di scaricare le guide per l'amministratore e i manuali d'uso del telefono del produttore.
  
- Per i telefoni Polycom, consulta la [Guida alla distribuzione di Polycom]((http://www.polycom.com/voice-conferencing-solutions/desktop-ip-phones.html).
    
- Per i telefoni Yealink, consulta [Soluzione con telefoni SIP HD Yealink per Skype for Business](http://www.yealink.com/products_top_2.html).
    
- Per i telefoni AudioCodes, consulta la [Guida alla gestione del provisioning Audiocodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions).
    
### <a name="step-2---make-sure-youre-purchasing-or-migrating-a-skype-for-business-supported-ip-phone-and-firmware"></a>Fase 2 - Assicurati di stare acquistando o migrando un telefono IP e firmware supportati da Skype for Business

Un telefono e firmware supportati da Skype for Business Online sono compatibili anche con Skype for Business Server, ma non è sempre vero il contrario. Per assicurarti di stare acquistando o mettendo in provisioning un telefono supportato e firmware supportati, consulta la guida [Ottenere telefoni per Skype for Business online](getting-phones-for-skype-for-business-online.md).
  
### <a name="step-3---checking-that-the-right-firmware-is-installed-and-update-the-firmware-if-required"></a>Fase 3 - Verifica che sia installato il firmware giusto e aggiorna il firmware, se necessario

Controlla la versione del firmware sui tuoi telefoni. Per:
  
- **Telefoni VVX Polycom**, vai a **Impostazioni** > **Stato** > **Piattaforma** > **Applicazione** > **Principale**.
    
- i **telefoni Yealink**, accedi a **Status** (Stato) sulla schermata principale del telefono.
    
- **Telefoni AudioCodes**, vai a **Menu** > **Stato dispositivo** > **Versione firmware** dalla schermata di avvio.
    
    > [!NOTE]
    > Per l'accesso remoto ai dettagli del telefono, consulta le guide per l'amministrazione del produttore. Consulta i link qui sopra per i manuali utente e i manuali del telefono. 
  
- I **telefoni Lync Phone Edition (LPE)**, accedi a **Menu** > **System Information** (Informazioni sul sistema) dalla schermata iniziale.
    
### <a name="step-4---device-update-considerations"></a>Fase 4 - Considerazioni sull'aggiornamento del dispositivo

> [!NOTE]
> Il firmware Polycom precedente alla versione 5.5.1.X aveva un meccanismo di blocco del dispositivo specifico per il produttore, che è stato sostituito con un'implementazione di "Phone-Lock" per Skype for Business. L'upgrade di un telefono da 5.4.X.X, protetto da "Device-Lock", a 5.5.1.X con "Phone-Lock" non eredita il codice PIN da "Device-Lock", il che può lasciare il telefono non protetto. Gli utenti che hanno attivato "Device-Lock", devono abilitare il seguente parametro del profilo dispositivo Polycom per dare agli utenti il controllo nel momento dell'upgrade (lync.deviceUpdate.popUpSK.enabled=1). 
  
Gli upgrade del firmware sono gestiti dal servizio Skype for Business Service. Ogni firmware del telefono certificato Skype for Business viene caricato sul server Skype for Business Update e gli aggiornamenti dispositivo sono attivati su tutti i telefoni per impostazione predefinita. A seconda del tempo di inattività sul telefono e degli intervalli di polling, i telefoni scaricano e installano automaticamente l'ultima build certificata. Puoi disabilitare le impostazioni di aggiornamento del dispositivo utilizzando il cmdlet [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) e impostando il parametro _EnableDeviceUpdate_ a `false`.
  
![Distribuzione di telefoni.](../../images/be727622-1924-439f-96ca-89230739db9e.png)
  
Quando un nuovo firmware è disponibile e pronto per il download e l'installazione, il telefono avviserà l'utente. I telefoni Polycom potranno informare l'utente e fornirgli la possibilità di **aggiornare** o **rinviare**.
  
![Distribuzione di telefoni.](../../images/50956fa0-da0c-4085-9bb5-4a2e99aecebb.png)
  
Per un telefono Polycom, è possibile aggiornare il firmware del telefono selezionando **SwUpdate**.
  
![Distribuzione di telefoni.](../../images/376c1998-6ce6-44b6-a84d-ae7d96b1c307.png)
  
Puoi anche scegliere di gestire gli aggiornamenti del firmware utilizzando un sistema di provisioning partner. Per la gestione del sistema di provisioning partner, compresa la personalizzazione avanzata del telefono, consulta le guide per l'amministratore del produttore.
  
> [!CAUTION]
> Assicurati di avere un'unica autorità di aggiornamento dispositivi (aggiornamento del dispositivo in banda o server di provisioning di terze parti) per evitare loop di aggiornamento. 
  
### <a name="step-5---configuration-and-infrastructure-phone-settings"></a>Fase 5 - Configurazione e infrastruttura delle impostazioni del telefono

Puoi impostare le opzioni e i criteri del telefono più comunemente utilizzati che utilizzano i cmdlet di Windows PowerShell per la gestione in banda di Skype for Business. Consulta [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) per i dettagli di questi parametri e impostazioni.
  
Per la pianificazione delle infrastrutture di rete, consulta [Skype Operations Framework](https://www.skypeoperationsframework.com/).
  
### <a name="step-6---preparing-for-users-to-sign-in"></a>Fase 6 - Preparazione per l'accesso degli utenti

Per consentire agli utenti di accedere a un telefono Skype for Business online ed effettuare chiamate, devi assicurarti che agli utenti vengano assegnate le licenze corrette. Come minimo devi assegnare una licenza di Sistema telefonico e un Piano di chiamata. Per ulteriori informazioni, consulta [Licenze per i componenti aggiuntivi Skype for Business](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md) e [Assegnare le licenze Skyper for Business e Microsoft Teams](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).
  
Per ulteriori informazioni sui Piani di chiamata, consulta [Cosa sono i Piani di chiamate in Office 365?](/microsoftteams/what-are-calling-plans-in-office-365)
  
- Le **opzioni di accesso** disponibili per gli utenti online son le seguenti.
    
  - Gli utenti con telefoni **Polycom VVX 5XX/6XX** vedranno quanto segue:
    
     ![Distribuzione di telefoni.](../../images/8a1ffb33-8a63-4242-bb76-d5fafb6a6472.png)
  
  - Gli utenti con telefoni **Yealink T48G/T46G** vedranno quanto segue:
    
     ![Accesso telefoni Yealink.](../../images/2a2892ae-850d-4781-8be0-4ffb8af068c9.png)
  
    Per dettagli sulle opzioni di accesso supportate dei produttori, consulta [Ottenere telefoni per Skype for Business online](getting-phones-for-skype-for-business-online.md).
    
- **ID utente** Utilizzando la tastiera del telefono o la tastiera a schermo (se disponibile), gli utenti possono utilizzare il nome utente e la password della propria organizzazione per accedere al telefono. Ad esempio, possono utilizzare il formato UPN come *amosm@contoso.com*  per il nome utente.
    
     ![Distribuzione di telefoni.](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
    > [!NOTE]
    > L'autenticazione PIN non è supportata per Skype for Business online per i telefoni IP LPE e Partner. 
  
- **Utilizzando un PC** Quando il software Better Together over Ethernet (BToE) è installato sul PC dell'utente ed è abilitato, gli utenti possono accedere al proprio telefono utilizzando la finestra di autenticazione sull'app Skype for Business per Windows. Per ulteriori informaioni, consulta [Fase 7 (opzionale) - Con accoppiamento dispositivo e Better Together over Ethernet (BToE)](deploying-skype-for-business-online-phones.md#BK_BTOE).
    
    > [!NOTE]
    > Gli utenti devono utilizzare il nome utente e la password della propria organizzazione per accedere al telefono. Ad esempio, possono utilizzare il formato UPN come  *amosm@contoso.com*  per il nome utente.
  
     ![Distribuzione di telefoni.](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
- **Utilizzando Accesso Web** Questo è un nuovo modo per gli utenti online di autenticarsi utilizzando un browser Web standard. Gli utenti riceveranno una serie di istruzioni da seguire quando utilizzano un browser per l'accesso.
    
  - Gli utenti con telefoni **Polycom VVX 5XX/6XX** vedranno quanto segue:
    
     ![Distribuzione di telefoni.](../../images/ba0df923-a6e5-4a9b-b40b-b03ca188e814.png)
  
  - Gli utenti con telefoni **Yealink T48G/T46G** vedranno quanto segue:
    
     ![Accesso telefoni Yealink.](../../images/86551cc3-533a-4694-9683-bad907c9ad5a.png)
  
    Il codice che viene generato scadrà in 15 minuti. Alla scadenza, l'utente dovrà fare clic su **Riprova** o su **OK** per generare un nuovo codice, a seconda del telefono.
    
  - Gli utenti con telefoni **Polycom VVX 5XX/6XX** vedranno quanto segue:
    
     ![Codice PIN scaduto.](../../images/b5d27037-aa26-4054-be95-d5a6c293d08c.png)
  
  - Gli utenti con telefoni **Yealink T48G/T46G** vedranno quanto segue:
    
     ![Accesso telefoni Yealink.](../../images/3a4462ac-0c59-409e-a3bb-1451cdcc8676.png)
  
    Utilizzando un browser, accedi all'indirizzo visualizzato sul telefono e inserisci il tuo nome utente Skype for Business.
    
     ![Distribuzione di telefoni.](../../images/7c540b85-dc37-4ce7-a077-9e3454a0efd0.png)
  
    Immetti il codice mostrato sul telefono.
    
     ![Distribuzione di telefoni.](../../images/d6b88016-35d2-41d1-a0da-81fef34521d4.png)
  
    Verifica che il sito indichi "**Telefono certificato Skype for Business** [nome del produttore del telefono]" e fai clic su **Continua**.
    
     ![Distribuzione di telefoni.](../../images/a8252b37-4ff5-4ece-9e2a-3e05bf928299.png)
  
    Fai clic sulle credenziali dell'utente o fai clic su **Usa un altro account**:
    
     ![Distribuzione di telefoni.](../../images/8415028b-7924-4747-b639-052d9b0b961e.png)
  
    Quando viene visualizzata la pagina seguente, è consigliabile chiudere il browser.
    
     ![Distribuzione di telefoni.](../../images/1a873201-52fc-4a63-b7b5-e82bbd031fd2.png)
  
    > [!NOTE]
    > I telefoni LPE per Skype for Business online supportano l'accesso solo attraverso tethering USB. 
  
- **Distribuzioni supportate** La tabella seguente mostra i tipi di autenticazione supportati per i modelli di distribuzione attualmente supportati tra cui integrazione Exchange, autenticazione moderna con autenticazione a più fattori (MFA) e Skype for Business online e locale.
    
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Skype for Business** <br/> |**Exchange** <br/> |**Metodo di accesso telefono** <br/> |**Accesso Skype for Business** <br/> |**Accesso Exchange con autorizzazione moderna e MFA disattivate** <br/> |**Accesso Exchange con autorizzazione moderna e MFA attivate** <br/> |
|Online  <br/> |Online  <br/> |Accesso Web  <br/> |Sì  <br/> |Sì  <br/> |Sì  <br/> |
|Online  <br/> |Online  <br/> |Nome utente/password  <br/> |Sì  <br/> |Sì  <br/> |No  <br/> |
|Online  <br/> |Locale  <br/> |Accesso Web  <br/> |Sì  <br/> |No  <br/> |No  <br/> |
|Online  <br/> |Locale  <br/> |Nome utente/password  <br/> |Sì  <br/> |Sì  <br/> |No  <br/> |
|Locale  <br/> |Online/locale  <br/> |Autenticazione PIN  <br/> |Sì  <br/> |No  <br/> |No  <br/> |
|Locale  <br/> |Online/locale  <br/> |Nome utente/password  <br/> |Sì  <br/> |Sì  <br/> |N/D  <br/> |
|Locale  <br/> |Online/locale  <br/> |Accesso via PC (BTOE)  <br/> |Sì  <br/> |Sì  <br/> |N/D  <br/> |
   
- **Funzionalità del telefono** Il set di funzionalità può variare leggermente in base al partner del telefono IP. Per la serie di funzionalità completa e per ulteriori informazioni sulle funzionalità per ogni produttore di telefono, consulta [Ottenere telefoni per Skype for Business online](getting-phones-for-skype-for-business-online.md).
    
- **Phone-Lock** è una funzionalità di recente introduzione nei telefoni certificati Skype for Business che permette di proteggere un telefono. Se è abilitata, gli utenti saranno invitati a creare un PIN una volta eseguita l'autenticazione. Una volta creato il PIN, il telefono si blocca quando scade un periodo di inattività definito, quando l'utente blocca manualmente il telefono o quando sincronizza il proprio Phone-Lock con il blocco su PC utilizzando l'accoppiamento del telefono. Se il PIN Phone-Lock viene inserito più volte in modo errato, il telefono disconnette l'utente o richiede il codice di un amministratore per sbloccare il telefono (questo può variare a seconda del partner che produce il telefono). Il PIN dell'utente deve essere composto di un numero di cifre compreso tra 6 e 15.
    
    Phone-Lock è attivato per impostazione predefinita per l'organizzazione, ma può essere disattivato. Inoltre, è possibile modificare il timeout di inattività e scegliere se gli utenti possono effettuare chiamate mentre sono bloccati o non usano impostazioni in banda. Per ulteriori informazioni su queste impostazioni, consulta [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx).
    
## <a name="step-7-optional---if-you-have-device-pairing-and-better-together-over-ethernet-btoe"></a>Fase 7 (opzionale) - Con accoppiamento dispositivo e Better Together over Ethernet (BToE)
<a name="BK_BTOE"> </a>

BToE è un meccanismo di accoppiamento telefoni per i telefoni IP partner che accoppia un telefono dell'utente con l'app Skype for Business per Windows. BToE consente agli utenti di:
  
- accedere al proprio telefono IP utilizzando l'applicazione desktop Skype for Business (utilizzando un PC)
    
- sincronizzare Blocco telefono con il blocco PC
    
- chiamare con un clic
    
BToE può essere configurato per operare in due modalità:  *Auto*  (impostazione predefinita) e *Manuale*. Può anche essere abilitato (impostazione predefinita)/disabilitato per gli utenti che utilizzano le impostazioni in banda di Skype for Business. In modalità *Manuale*, gli utenti dovranno eseguire un ulteriore passaggio per accoppiare il telefono all'app su Windows.
  
 **Per distribuire BToE agli utenti**
  
1. Collegare il PC al telefono utilizzando la porta del PC.
    
     ![Distribuzione di telefoni.](../../images/e21d76c7-867c-4fe6-95c6-fc40c608ed0c.png)
  
2. Scaricare e installare l'ultima versione del software BToE dal sito web del produttore dai link qui sotto. Per una migliore esperienza utente, è possibile distribuire e installare il software BToE utilizzando una soluzione di distribuzione di amministrazione come System Center Configuration Manager (SCCM). Per informazioni sull'utilizzo di SCCM, consulta [Pacchetti e programmi in System Center Configuration Manager](https://docs.microsoft.com/en-us/sccm/apps/deploy-use/packages-and-programs).
    
  - [Sito di download software BToE Polycom](http://www.polycom.com/voice-conferencing-solutions/microsoft-phones.html)
    
  - [Download software BToE Yealink](http://www.yealink.com/products_list_10.html)
    
  - [Download software BToE AudioCodes](https://www.audiocodes.com/solutions-products/solutions/skype-for-business-microsoft-teams/skype-for-business-online)
    
3. La configurazione del server per BToE è impostata su **Abilitato** e **Modalità automatica** come impostazione predefinita. Per modificare le impostazioni, consulta [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx).
    
> [!NOTE]
> BToE non è attualmente supportato su piattaforme Mac e VDI. 
  
## <a name="related-topics"></a>Argomenti correlati
[Ottenere numeri di servizio per Skype for Business e Microsoft Teams](../../what-is-phone-system-in-office-365/getting-service-phone-numbers.md)

[Ecco cosa offre il Sistema telefonico in Office 365](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[Disponibilità di Audioconferenza e Piani per chiamate per paese e area geografica](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

  
 
