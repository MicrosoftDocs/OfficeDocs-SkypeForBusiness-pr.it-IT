---
title: Supporto per la migrazione della messaggistica unificata online di Exchange
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: waseemh, dstrome, balinger
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Microsoft sta ritirando il servizio Exchange Unified Messaging online (ExchUMO) entro il 2020 febbraio. In questo articolo vengono riepilogate le informazioni che i clienti interessati dovrebbero conoscere e fare per pianificare la continuità aziendale.
ms.openlocfilehash: 6fe0436d0ae4df2b4eb56a3c84319770b45f3139
ms.sourcegitcommit: b8e16703e4611ca2bde55896ec158b33be4f9ba0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2019
ms.locfileid: "39842468"
---
# <a name="exchange-unified-messaging-online-migration-support"></a>Supporto per la migrazione della messaggistica unificata online di Exchange

In riferimento all' [annuncio](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-unified-messaging-in-exchange-online/) dell'8 febbraio 2019, Microsoft sta ritirando il servizio Exchange Unified Messaging online (ExchUMO) entro il febbraio 2020. Questo articolo offre un riepilogo delle informazioni che i clienti interessati dovrebbero conoscere e fare per pianificare la continuità aziendale.
 
ExchUMO è distribuito dai clienti per la segreteria telefonica, l'operatore automatico, la coda delle chiamate e i servizi di integrazione fax. Microsoft prevede di aiutare i clienti a eseguire la migrazione a servizi di sistema telefonico che supportano già migliaia di clienti in Skype for business online e Microsoft teams.

La segreteria telefonica è principalmente una migrazione basata su Microsoft; il coinvolgimento degli amministratori e/o gli investimenti potrebbero essere necessari per un sottoinsieme di clienti. Operatore automatico è una migrazione guidata dall'amministratore; dovrai ricreare gli alberi di operatore automatico di ExchUMO esistenti nel servizio cloud di operatore automatico cloud. I clienti che usano qualsiasi funzionalità di ExchUMO con un PBX di terze parti non verranno migrati in servizi cloud Skype perché non supportano sistemi PBX di terze parti. In [questo Blog](https://techcommunity.microsoft.com/t5/Exchange-Team-Blog/New-date-for-discontinuation-of-support-for-Session-Border/ba-p/607853)è stato annunciato un piano pensionistico per il supporto di terze parti e i clienti di questo modello di distribuzione possono eseguire la migrazione degli utenti a una delle piattaforme/servizi Microsoft Unified Communications o acquisire una segreteria telefonica di terze parti e/o una soluzione di operatore automatico per questi utenti. L'integrazione fax non è supportata nei servizi basati sul cloud. i clienti dovranno eseguire la migrazione a una soluzione di terze parti.

### <a name="who-is-affected"></a>Chi è interessato?

I clienti che utilizzano una delle caratteristiche seguenti del servizio messaggistica unificata di Exchange sono interessati:

- Servizio di segreteria telefonica
- Servizio operatore automatico
- Servizio code di chiamata
- Integrazione fax

> [!Note]
> I clienti che usano qualsiasi server Exchange locale con la messaggistica unificata non sono interessati. 

Leggi altre informazioni sull'impatto dell'esperienza utente e dell'amministratore nell' [impatto sull'esperienza utente](#user-experience-impact).

## <a name="migration-plan-overview"></a>Panoramica del piano di migrazione

Microsoft ha identificato varie distribuzioni di clienti che stanno consumando funzionalità da ExchUMO e aiuteranno i clienti a eseguire la migrazione in base al piano seguente. 

|Gruppo di clienti |Sequenza temporale  |Dettagli  |
|---------|---------|---------|
|Clienti pronti per la migrazione<br><br>Caratteristiche di migrazione:<br><ul><li>Segreteria telefonica</ul>   |   Marzo-maggio 2019  |Esempi<ul><li>    Clienti con la distribuzione e l'utilizzo della segreteria telefonica semplice<li>Clienti con tutti i requisiti stabiliti per Microsoft per eseguire la migrazione<ul>|
|Clienti con prerequisiti<br><br>Caratteristiche di migrazione:<br><ul><li>Segreteria telefonica<li>Operatore automatico<li>Coda di chiamata</ul> |  Maggio-dicembre 2019 |Esempi <br><ul><li>La configurazione ibrida non è completa<li>I numeri PSTN ibridi non sono configurati</ul>|
|Clienti che richiedono coinvolgimento dell'amministratore & investimento del cliente<br><br>Caratteristiche di migrazione:<ul><li>segreteria telefonica<li>Operatore automatico<li>Code di chiamata<li>Integrazione fax</ul>| Entro il 2020 febbraio  | Esempi <br><ul><li>Il servizio ExchUMO viene utilizzato da PBX di terze parti<li>Clienti con requisiti di accesso per gli abbonati PSTN<li>Clienti in SFB 2010 (non supportati)<li>Integrazione fax</ul> |

## <a name="voicemail-migration-steps"></a>Passaggi di migrazione della segreteria telefonica

1.  **Ottenere informazioni**
 
    Familiarizzare con l' [annuncio di Blog](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-unified-messaging-in-exchange-online/) e questo articolo per pianificare una migrazione uniforme per gli utenti. Vedere [controllare la segreteria telefonica di Skype for business e le opzioni](https://support.office.com/article/check-skype-for-business-voicemail-and-options-2deea7f8-831f-4e85-a0d4-b34da55945a8) per informazioni dettagliate sulle funzionalità della segreteria telefonica del sistema telefonico.  
 
2.  **Creare una topologia ibrida di Skype for business**

    Se non si ha una topologia ibrida di Skype for business, è necessario farlo per consentire una migrazione fluida degli utenti della segreteria telefonica. Per altre informazioni, vedere [Configurare Skype for business Hybrid](../../SfbHybrid/hybrid/configure-federation-with-skype-for-business-online.md) . 

    > [!Note]
    > Non è necessario eseguire la migrazione degli utenti a online per la migrazione del servizio della segreteria telefonica. Tuttavia, per gli utenti locali per sfruttare il servizio di segreteria telefonica del sistema telefonico, è necessario stabilire una topologia ibrida.

3. **Pianificare la migrazione di operatore automatico**
    
    Gli amministratori possono iniziare a migrare gli operatori automatici da ExchUMO all'operatore automatico cloud in qualsiasi momento. Per altre informazioni, vedere [configurare un operatore automatico cloud](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant) . Microsoft continua a fornire funzionalità di operatore automatico aggiuntive che i clienti possono considerare necessarie per la migrazione, gli amministratori dovrebbero valutare il set di caratteristiche e eseguire la migrazione delle istanze di operatore automatico di conseguenza. Per il confronto tra elenchi di funzionalità, vedi la [matrice di caratteristiche dei servizi basati su cloud ExchUMO e Azure](#exchumo-and-azure-cloud-based-services-feature-matrix).

4. **Pianificare la segreteria telefonica e i test di post-migrazione**

    La migrazione della segreteria telefonica è guidata da Microsoft. Gli amministratori non sono tenuti a eseguire alcuna operazione, poiché viene stabilita la topologia ibrida prerequisita. Microsoft esegue la convalida e i test necessari per verificare che la migrazione della segreteria telefonica degli utenti non venga interrotta. Gli amministratori sono invitati a eseguire test e convalida dalla loro parte. Vedere il [piano di test suggerito e la convalida post-migrazione per gli amministratori](#suggested-test-plan-and-post-migration-validation-for-admins) per un piano di test raccomandato. 

    > [!Note]
    > Lync Server 2010 non è supportato. Se si è in una distribuzione di 2010 Server, è consigliabile pianificare un aggiornamento del server o prendere in considerazione la possibilità di eseguire la migrazione degli utenti a Microsoft teams o Skype for business online.  

5. **Monitorare il centro notifiche di amministrazione**

    Cercare un avviso nel centro notifiche di amministrazione con ulteriori dettagli e sequenza temporale per quanto riguarda la migrazione degli utenti. Le notifiche vengono inviate almeno 30 giorni prima del periodo di migrazione. 

    > [!Note]
    > Se è stata ricevuta una notifica con la sequenza temporale di migrazione degli utenti e si vuole rinviare la migrazione per motivi aziendali, è possibile contattare il supporto tecnico Microsoft. Tieni presente che non puoi rinviare la migrazione oltre la data di pensionamento, 2020 febbraio. Per i clienti che potrebbero avere altre domande, contattare il team dell'account o il supporto tecnico Microsoft. I clienti che usano già Office 365 possono inviare un caso di supporto tramite il portale di amministrazione di Office 365. 

6. **Valutare la possibilità di optare per una migrazione pianificata**

    È possibile optare per una migrazione del servizio Voicemail pianificata in CVM. Prima di optare, rivedere i dettagli di questo articolo, in particolare le sezioni seguenti:

    - Passaggi di migrazione (questa sezione)
    - Matrice di funzionalità di servizi basati su cloud ExchUMO e Azure
    - Impatto sull'esperienza utente

    Quando si sceglie una migrazione gestita, non si riceverà una notifica di pre-migrazione di 30 giorni nel centro messaggi del portale di amministrazione di Microsoft 365.
 
    Per optare per una migrazione pianificata, inviare una richiesta di posta elettronica dall'indirizzo di posta elettronica dell'amministratore a [CVM@microsoft.com](mailto:cvm@microsoft.com) con le informazioni seguenti:

    - Data preferita (martedì): le onde di migrazione vengono eseguite ogni martedì. Selezionare una data in un martedì non superiore a 12/3/2019.
 
    - ID tenant: numero di caratteri di 32 in questo formato 0046728c-688a-4472-a38f-098fec60ac6x. È possibile trovare l'ID tenant nel portale di amministrazione di Microsoft 365 in Azure AD o usando il cmdlet di PowerShell seguente:`Get-CsTenant | Select ObjectId`
 
    Si riceve una conferma tramite posta elettronica dopo la migrazione del tenant.

## <a name="auto-attendant-migration-guidelines"></a>Linee guida per la migrazione di operatore automatico

Gli amministratori del tenant di Office 365 sono tenuti a ricreare gli operatori automatici di Exchange UM online nel servizio Microsoft Cloud Auto Attendant e a scambiarsi i loro numeri di telefono locali prima del 1 ° febbraio 2020, che si verifica quando il servizio di Exchange UMO sarà ritirato. Ecco le linee guida consigliate per eseguire correttamente la migrazione e testare nuovi operatori automatici cloud. Se si ha un numero elevato di operatori automatici, è possibile usare l' [operatore automatico di messaggistica unificata di Exchange per gli script di migrazione degli operatori](https://github.com/NathanJBennett/ExUMAAMigrationToCloudAA) automatici del cloud per semplificare la migrazione in blocco degli operatori automatici.

### <a name="setup"></a>Configurazione

Ti consigliamo vivamente di avviare prima la configurazione dei nuovi operatori automatici per evitare problemi relativi all'ultimo minuto e acquisire familiarità con le funzionalità e l'esperienza del servizio operatore automatico cloud. Per gli operatori automatici che richiedono una o più funzionalità Gap, è possibile creare e testare gli operatori automatici quando le caratteristiche Gap sono disponibili per la preparazione della distribuzione. Per altre informazioni sulle caratteristiche di Gap, vedere l' [appendice](#appendix).

1. Usare i cmdlet di Exchange UMO per esportare la configurazione degli operatori automatici esistenti tramite [Get-UMAutoAttendant](https://docs.microsoft.com/powershell/module/exchange/unified-messaging/get-umautoattendant).  
2. Usare il cmdlet [Export-UMprompt](https://docs.microsoft.com/powershell/module/exchange/unified-messaging/export-umprompt) in PowerShell di Exchange Online per esportare i file multimediali di saluto (se usati) e convertirli in formato mp3.
3. Seguire le istruzioni in [pianificare gli operatori automatici del cloud](../../SfbHybrid/hybrid/plan-cloud-auto-attendant.md) e [configurare un operatore automatico cloud](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant) per creare gli operatori automatici usando l'interfaccia di amministrazione di Microsoft teams o PowerShell.
4. Esaminare i messaggi di saluto se sono state modificate le opzioni del menu.
5. Configurare i trasferimenti per i gruppi di risposte usando la soluzione "trasferimento automatico di chiamata tramite operatore PSTN" nella sezione [problemi noti](#known-issues) di questo articolo.  
6. Testare i nuovi operatori automatici. Per eseguire il test, chiamali internamente o assegna un numero di telefono di prova.  

### <a name="cutover"></a>Completa

1. Cambiare i numeri di telefono dagli operatori automatici di Exchange UMO ai nuovi operatori automatici.
2. Consente di trasferire l'URI SIP dall'oggetto contatto all'account delle risorse.
3. Testare e convalidare gli operatori automatici usando i numeri di telefono appena assegnati. 

## <a name="appendix"></a>Appendice

### <a name="exchumo-and-azure-cloud-based-services-feature-matrix"></a>Matrice di funzionalità di servizi basati su cloud ExchUMO e Azure

| Servizio | Livello di funzionalità | Funzionalità | Note  | Cloud VM/AA  | ExUMO |
|---------|-------|--------|----|--------|------|
| VM  | Caratteristiche del servizio| Supporto PBX di terze parti    | Inclusione di tutte le caratteristiche fornite a PBX di terze parti, ad esempio MWI (Message Waiting Indicator) con i messaggi SIP NOTIFY di Exchange UM online | N   | Y    |
| VM | Caratteristiche del servizio  | Supporto di Skype for Business Server   |  | Y | Y    |
| VM | Caratteristiche del servizio | Supporto di Microsoft Teams|  | Y | N    |
| VM | Caratteristiche del servizio | eDiscovery e tieni premuto  | Per la sicurezza e la conformità  | Y | Y    |
| VM | Caratteristiche del servizio | Supporto di Exchange Rules | Per la sicurezza e la conformità  | Y | Y    |
| VM | Caratteristiche utente | Accesso telefonico PSTN  | Accesso sottoscrittore  | N | Y    |
| VM | Caratteristiche utente | Outlook Voice Access PSTN   | Accesso sottoscrittore  | N | Y    |
| VM | Caratteristiche utente | Accesso esterno con un endpoint autenticato | Chiamata del servizio segreteria telefonica per ascoltare i messaggi vocali e modificare le impostazioni della segreteria telefonica| Y | Y    |
| VM | Caratteristiche utente | Impostazione utente per disabilitare la segreteria telefonica   |  | Y | Y    |
| VM | Caratteristiche utente | Impostazione utente per cambiare il messaggio di saluto personale  |  | Y | Y    |
| VM | Caratteristiche utente | Impostazione utente per creare un messaggio fuori sede  |  | Y | Y    |
| VM | Caratteristiche utente | Impostazione utente per modificare la lingua predefinita  |  | Y | Y    |
| VM | Caratteristiche utente | Impostazione utente per sovrascrivere il messaggio di saluto predefinito con TTS  |  | Y | N    |
| VM | Caratteristiche utente | Registrare i saluti personali (dispositivo autenticato) |  | Y | Y    |
| VM | Caratteristiche utente | Registrare i saluti personali (PSTN)-Play al telefono |  | N | Y    |
| VM | Caratteristiche utente | Impostazione utente per disabilitare la trascrizione |  | N | Y    |
| VM | Caratteristiche utente | Trascrizione  |  | Y | Y    |
| VM | Caratteristiche utente | Voicemail visivo in tutti gli endpoint   | Con il controllo utente per la riproduzione, l'eliminazione, l'indicatore di attesa del messaggio e l'attivatore di stato, in tutti gli endpoint supportati  | Y | Y    |
| VM | Caratteristiche utente | Formato di file audio MP3 in Outlook    |  | Y | Y    |
| VM | Caratteristiche utente | Controllo velocità di riproduzione variabile |  | Y | Y    |
| VM | Caratteristiche utente | Inoltrare un messaggio vocale  | Inoltrare un messaggio vocale ricevuto ad altri utenti | Y | Y    |
| VM | Caratteristiche utente | Invio di un messaggio vocale a un gruppo di utenti  |Trasmissione della segreteria telefonica   | N | Y   |
| VM | Caratteristiche utente | Notifica della segreteria telefonica tramite SMS    | Gli utenti possono ricevere un SMS quando hanno un nuovo messaggio vocale    | N | Y    |
| VM | Caratteristiche utente | Lingue di saluto supportate | Dettagli qui:https://docs.microsoft.com/microsoftteams/what-are-phone-system-auto-attendants | Y | Y    |
| VM | Caratteristiche utente | Regole di risposta alle chiamate |  | Y | Y    |
| VM | Caratteristiche utente | Riproduci su telefono (PSTN)-per riprodurre il messaggio | Chiamami nella cella per ascoltare il messaggio vocale  | N | Y    |
| VM | Caratteristiche utente | Riproduci sul telefono (auth)-per riprodurre il messaggio | Chiamami nel dispositivo autenticato  | Y | Y    |
| VM | Caratteristiche utente | Cassetta postale condivisa tra più utenti |  | Y | Y    |
| VM | Caratteristiche del chiamante  | Esperienza chiamante: voicemail protetto | Il chiamante può scegliere un'opzione per contrassegnare un messaggio registrato come protetto| N | Y    |
| VM | Caratteristiche del chiamante  | Esperienza chiamante-segreteria telefonica privata | Il chiamante può scegliere un'opzione per contrassegnare un messaggio registrato come privato  | N | Y    |
| VM | Caratteristiche del chiamante  | Rilevazione silenzio   |  | N | Y    |
| VM | Caratteristiche di amministratore tenant | Segreteria telefonica protetta a livello di server    | Tenant-admin può configurare una regola a livello di servizio per contrassegnare la segreteria telefonica in arrivo come protetta | Y | Y    |
| VM | Caratteristiche di amministratore tenant | Modificare il limite di durata della registrazione  |     | Y | Y    |
| VM | Caratteristiche di amministratore tenant | Modificare il timeout di rilevamento del silenzio    |  | N/D    | Y    |
| VM | Caratteristiche di amministratore tenant | Modificare il numero di errori di input | CVM: hardcoded in 3 | N | Y    |
| VM | Caratteristiche di amministratore tenant | Modificare la lingua predefinita |  | Y | Y    |
| VM | Caratteristiche di amministratore tenant | Disabilitare/abilitare la trascrizione |  | Y | Y    |
| VM | Caratteristiche di amministratore tenant | Disabilitare/abilitare la notifica di chiamata senza risposta |  | N | Y    |
| VM | Caratteristiche di amministratore tenant | Guida di Microsoft per migliorare l'anteprima della segreteria telefonica    |  | Y | Y    |
| VM | Caratteristiche di amministratore tenant | Personalizzare il messaggio di testo per gli utenti abilitati|  | N/D    | Y    |
| VM | Caratteristiche di amministratore tenant | Mascheramento profanità trascrizione|  | Y | N    |
| VM | Caratteristiche di amministratore tenant | Criteri per la segreteria telefonica    |   | Y | Y    |
| VM | Caratteristiche di amministratore tenant | Amministrazione portale Web   |  | CY19   | Y    |
| VM | Caratteristiche di amministratore tenant | PowerShell   |  | Y | Y    |
| AA | Caratteristiche del servizio | Supporto di terze parti PBX di AA    |  | N | Y    |
| AA | Caratteristiche del servizio | Supporto di Skype for Business Server   |  | Y | Y    |
| AA | Caratteristiche del servizio | Supporto di Microsoft Teams|  | Y | N    |
| AA | Caratteristiche del servizio | Chiamata per nome, input DTMF    |  | Y | Y    |
| AA | Caratteristiche del servizio | Chiamata per nome, input vocale  |  | Y | Y    |
| AA | Caratteristiche del servizio | Supporto multilingue | Dettagli della lingua qui:https://docs.microsoft.com/microsoftteams/what-are-phone-system-auto-attendants | Y | Y    |
| AA | Caratteristiche del servizio | Trasferimento all'operatore, CQ o un utente |  | Y | Y    |
| AA | Caratteristiche del servizio | Trasferire al numero PSTN internamente (DID RNL)  |  | Y | Y    |
| AA | Caratteristiche del servizio | Trasferire al numero PSTN esternamente  |  | Sezione problemi noti di seguito | Y    |
| AA | Caratteristiche del servizio | Orari di ufficio |  | Y | Y    |
| AA | Caratteristiche del servizio | Opzioni di menu | Opzioni del menu IVR  | Y | Y    |
| AA | Caratteristiche del servizio | Assegnazione di un numero PSTN cloud a AA |  | Y | N    |
| AA | Caratteristiche del servizio | Assegnazione di un numero PSTN on-Prem a AA  |  | Y | Y    |
| AA | Caratteristiche del servizio | Selezione utente personalizzata  | Consentire ai chiamanti di raggiungere un elenco personalizzato di utenti dell'organizzazione| Y | Y    |
| AA | Caratteristiche del servizio | Trattamento after-hours and Holidays  |  | Y | Y    |
| AA | Caratteristiche del servizio | Messaggio di saluto personalizzato con testo in sintesi vocale  |  | Y | Y    |
| AA | Caratteristiche del servizio | Chiamata di estensione   | Raggiungimento di un utente tramite la chiamata dell'estensione  | Y   | Y    |
| AA | Caratteristiche del servizio | Cassetta postale per i chiamanti AA per uscire da un messaggio    |  | CY19   | Y    |
| AA | Caratteristiche del servizio | Più assegnazioni di numeri PSTN a un AA|  | Y | Y    |
| AA | Caratteristiche di amministratore tenant | Amministrazione portale Web   |  | Y | N    |
| AA | Caratteristiche di amministratore tenant | Cmdlet di PowerShell  |  | Y | Y    |
| Fax| Caratteristiche del servizio | Integrazione fax|  | N | Y    |

### <a name="suggested-test-plan-and-post-migration-validation-for-admins"></a>Piano di test suggerito e convalida post-migrazione per gli amministratori

Per verificare che gli utenti siano stati migrati nel cloud voicemail, lasci un messaggio vocale a un utente e controlli il corpo del messaggio in Outlook.  I messaggi di segreteria telefonica cloud hanno un piè di pagina che recita:

**Grazie per aver usato la trascrizione. Se non si vede una trascrizione sopra, è perché la qualità audio non è abbastanza chiara da trascrivere.**

Quando si verifica la funzionalità della segreteria telefonica dopo la migrazione degli utenti, verificare gli scenari seguenti:

- Convalidare l'accesso alla segreteria telefonica in tutti i tipi di endpoint dell'organizzazione: app e telefoni IP. 
- Convalidare con gli utenti di esempio che i messaggi di saluto personalizzati configurati vengono riprodotti ai chiamanti.   
- Se l'organizzazione ha un requisito legale o di conformità per disabilitare la trascrizione per gli utenti, verificare che sia disabilitata dopo la migrazione. Per altre informazioni, vedere [configurare la segreteria telefonica cloud](/microsoftteams/set-up-phone-system-voicemail).
- Se in precedenza sono stati configurati criteri e regole della VM di Exchange, verificare che siano efficaci.
- Acquisire familiarità con i cmdlet di PowerShell per il servizio cloud Voicemail per la modifica delle impostazioni utente.  

### <a name="user-experience-impact"></a>Impatto sull'esperienza utente

Di seguito è riportata una panoramica dell'esperienza di migrazione della segreteria telefonica dell'utente finale.


|Esperienza  |Modifica dell'esperienza utente|
|---------|---------|
|Notifica tramite posta elettronica | Nessun cambiamento<br>Non viene inviato alcun messaggio di posta elettronica agli utenti che notificano l'attivazione/migrazione dell'account della segreteria telefonica. |
|Accesso ai messaggi precedenti | Nessun cambiamento<br>Gli utenti possono accedere ai messaggi della segreteria telefonica precedente in tutti gli endpoint supportati. |
|Ricezione di VM in Outlook, app SFB| Nessun cambiamento<br>Gli utenti continuano a ricevere i messaggi della segreteria telefonica in tutti gli endpoint supportati. |
|Trascrizione | Avanzato<br>La trascrizione di CVM ha un tasso di accuratezza molto più elevato e lingue supportate rispetto a ExchUMO. |
|Impostazione utente | Nuova esperienza<br>Gli utenti possono modificare le proprie preferenze da un portale di impostazioni utente (USP). Gli utenti possono accedere al proprio USP da un collegamento ipertestuale nella posta elettronica della segreteria telefonica o dal pulsante Impostazioni utente nel client di SFB; https://aka.ms/vmsettings.   
 |Caratteristiche| Vedere il confronto tra set di caratteristiche per i dettagli. |
|Regole di Outlook per i messaggi VM | Nessun cambiamento<br>Le regole create in precedenza si applicano ai messaggi di CVM dopo la migrazione.
 |

#### <a name="user-management-and-provisioning-in-cvm"></a>Gestione e provisioning degli utenti in CVM

I nuovi utenti di Skype for business verranno automaticamente provisionati per il cloud Voicemail quando vengono creati. Per eseguire il provisioning di nuovi utenti della segreteria telefonica non è necessario alcun ulteriore lavoro o licenza. Vedere [configurare la segreteria telefonica cloud](/microsoftteams/set-up-phone-system-voicemail) per informazioni sulla gestione dei criteri per gli utenti esistenti e quelli nuovi.

#### <a name="admin-auto-attendant-management-experience"></a>Esperienza di gestione dell'operatore automatico di amministrazione

Per altre informazioni sugli operatori automatici, vedere [configurare un operatore automatico cloud](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant).

#### <a name="known-issues"></a>Problemi noti

**Trasferimento automatico delle chiamate all'operatore PSTN** I clienti sono invitati a configurare una soluzione temporanea per soddisfare i requisiti per il trasferimento di una chiamata di operatore automatico a un numero PSTN esterno o a un'istanza di RGS. 
 
È stato individuato un problema durante la garanzia della qualità con la caratteristica di trasferimento in numero PSTN, che non verrà fissata in tempo per consentire ai clienti di iniziare la migrazione da Exchange UMO Service prima della data di pensionamento programmata del 1 ° febbraio 2020. Come soluzione alternativa, gli amministratori possono trasferire i chiamanti dell'operatore automatico a un utente virtuale locale con un'impostazione di inoltro di chiamata attiva al numero di telefono PSTN desiderato o al numero di telefono RGS. 
 
Esperienza prevista
- Gli amministratori non devono concedere la licenza all'utente virtuale, poiché si tratta di una soluzione alternativa 
- Gli amministratori possono modificare l'ID chiamante che verrà visualizzato dal ricevitore PSTN assegnando il numero desiderato all'utente virtuale oppure usando le funzionalità di manipolazione delle cifre SBC
- I chiamanti PSTN non avranno alcun ritardo durante il trasferimento delle chiamate e continueranno a vedere l'ID chiamante dell'operatore automatico dopo il successo del trasferimento  

**Cassetta postale condivisa:** Una cassetta postale condivisa configurata tramite la messaggistica unificata di Exchange Online continuerà a ricevere i messaggi dopo la migrazione a CVM e continuerà ad essere accessibile agli utenti tramite Outlook. Tuttavia, l'accesso per modificare i messaggi di saluto delle cassette postali non sarà disponibile dopo la migrazione a CVM. I clienti con cassette postali condivise usate per acquisire i chiamanti dell'operatore automatico dovrebbero sfruttare le funzionalità degli operatori automatici e delle code di chiamata condivise delle cassette postali, una volta rilasciate (ETA ottobre 2019).
  
**Eseguire l'aggiornamento a banner Teams nel client di SFB:** Il servizio CVM si basa sull'infrastruttura di Microsoft Teams; le chiamate effettuate dal client Skype for business possono causare la visualizzazione di un banner informativo sul client che recita: "il nome utente non usa Skype for business. Per un'esperienza più dettagliata, passa a teams o avvia una riunione Skype.
Assicurati di aggiornare il client Skype for business degli utenti al più recente aggiornamento client di C2R per evitare che questo banner venga visualizzato.
  
**La configurazione della segreteria telefonica consente di eseguire l'installazione in OWA:** Se si fa clic su "Configura segreteria telefonica", il client continuerà a portare i clienti di Skype for Business Server 2015/2013 alla pagina del portale di Office Web Access (OWA) dopo la migrazione a CVM. Tutte le impostazioni sono state rimosse dalla scheda segreteria telefonica in OWA e un banner verrà visualizzato con un collegamento di reindirizzamento per consentire agli utenti di usare il portale delle impostazioni utente di CVM.
 
**Modificare l'accesso per dispositivi mobili:** L'accesso del sottoscrittore PSTN non è supportato in CVM. Per gli utenti che devono cambiare il loro saluto in remoto, viene aggiunta un'opzione di menu "cambia saluto" al servizio IVR della segreteria telefonica per i client mobili. Gli utenti possono chiamare questo servizio premendo e tenendo premuto il tasto "1" nella tastiera del client per dispositivi mobili.
