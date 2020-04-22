---
title: Supporto per la migrazione della messaggistica unificata di Exchange Online
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: waseemh, dstrome, balinger
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Microsoft sta ritirando il servizio di messaggistica unificata di Exchange Online (ExchUMO) entro il 28 febbraio 2020. In questo articolo vengono riepilogati i clienti coinvolti che devono conoscere e fare per pianificare la continuità aziendale.
ms.openlocfilehash: ab0040887b41fc62786f21c889f7dd63aae011b4
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780775"
---
# <a name="exchange-unified-messaging-online-migration-support"></a>Supporto per la migrazione della messaggistica unificata di Exchange Online

> [!IMPORTANT]
> **Il servizio messaggistica unificata in Exchange Online non è supportato al momento del 28 febbraio 2020 Pacifico. Tutti gli account della segreteria telefonica sono stati migrati al servizio cloud voicemail da Microsoft. Qualsiasi traffico operatore automatico rimanente non verrà monitorato e potrebbe essere interrotto in qualsiasi momento.**

In riferimento all' [annuncio](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-unified-messaging-in-exchange-online/) dell'8 febbraio 2019, Microsoft sta ritirando il servizio di messaggistica unificata di Exchange Online (ExchUMO) entro il 28 febbraio 2020. In questo articolo viene offerta una sintesi dei requisiti che i clienti coinvolti devono conoscere e fare per pianificare la continuità aziendale.
 
ExchUMO è distribuito dai clienti per la segreteria telefonica, l'operatore automatico, la coda di chiamata e i servizi di integrazione fax. Microsoft intende consentire ai clienti di eseguire la migrazione a servizi di sistema telefonico che supportano già migliaia di clienti su Skype for business online e Microsoft teams.

La segreteria telefonica è principalmente una migrazione basata su Microsoft. per un sottoinsieme di clienti, potrebbe essere necessario un coinvolgimento e/o un investimento di amministratore. Operatore automatico è una migrazione guidata dall'amministratore; sarà necessario ricreare gli alberi degli operatori automatici di ExchUMO esistenti nel servizio cloud per l'operatore automatico cloud. I clienti che utilizzano una qualsiasi delle funzionalità di ExchUMO con un sistema PBX di terze parti non verranno migrati ai servizi cloud di Skype perché non supportano sistemi PBX di terze parti. Un piano pensionistico per il supporto di terze parti è stato annunciato in [questo Blog](https://techcommunity.microsoft.com/t5/Exchange-Team-Blog/New-date-for-discontinuation-of-support-for-Session-Border/ba-p/607853)e i clienti di questo modello di distribuzione possono eseguire la migrazione degli utenti a una delle piattaforme/servizi Microsoft Unified Communications o acquisire una segreteria telefonica di terze parti e/o una soluzione operatore automatico per questi utenti. L'integrazione dei fax non è supportata nei servizi basati sul cloud. i clienti dovranno eseguire la migrazione a una soluzione di terze parti.

### <a name="who-is-affected"></a>Chi è influenzato?

I clienti che utilizzano una o più delle seguenti funzionalità dal servizio messaggistica unificata di Exchange sono coinvolti:

- Servizio segreteria telefonica
- Servizio operatore automatico
- Servizio code di chiamata
- Integrazione fax

> [!Note]
> I clienti che utilizzano uno qualsiasi dei server Exchange locali con la messaggistica unificata non sono intaccati. 

Per ulteriori informazioni, vedere l'utente e l'impatto sull'esperienza di amministratore nell' [impatto sull'esperienza utente](#user-experience-impact).

## <a name="migration-plan-overview"></a>Panoramica del piano di migrazione

Microsoft ha individuato diverse distribuzioni dei clienti che utilizzano funzionalità di ExchUMO e aiuteranno i clienti a eseguire la migrazione in base al piano seguente. 

|Gruppo clienti |Sequenza temporale  |Dettagli  |
|---------|---------|---------|
|Clienti pronti per la migrazione<br><br>Funzionalità di cui eseguire la migrazione:<br><ul><li>Segreteria telefonica</ul>   |   Marzo-maggio 2019  |Esempi:<ul><li>    Clienti con semplicità di distribuzione e utilizzo della segreteria telefonica<li>Clienti con tutti i requisiti stabiliti per Microsoft per eseguire la migrazione<ul>|
|Clienti con prerequisiti<br><br>Funzionalità di cui eseguire la migrazione:<br><ul><li>Segreteria telefonica<li>Operatore automatico<li>Coda di chiamata</ul> |  Maggio — dicembre 2019 |Esempi: <br><ul><li>La configurazione ibrida non è completa<li>I numeri PSTN ibridi non sono configurati</ul>|
|Clienti che richiedono coinvolgimento dell'amministratore & investimento del cliente<br><br>Funzionalità di cui eseguire la migrazione:<ul><li>Voicemail<li>Operatore automatico<li>Code di chiamata<li>Integrazione fax</ul>| Entro febbraio 2020  | Esempi: <br><ul><li>Il servizio ExchUMO è utilizzato da PBX di terze parti<li>Clienti con requisiti di accesso del sottoscrittore PSTN<li>Clienti su questo 2010 (non supportato)<li>Integrazione fax</ul> |

## <a name="voicemail-migration-steps"></a>Passaggi di migrazione della segreteria telefonica

1.  **Ottenere informazioni**
 
    Familiarizzare con l' [annuncio di Blog](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-unified-messaging-in-exchange-online/) e questo articolo per pianificare una migrazione agevole per gli utenti. Vedere [verificare la segreteria telefonica di Skype for business e le opzioni](https://support.office.com/article/check-skype-for-business-voicemail-and-options-2deea7f8-831f-4e85-a0d4-b34da55945a8) per informazioni dettagliate sulle funzionalità di segreteria telefonica del sistema telefonico.  
 
2.  **Creare una topologia ibrida di Skype for business**

    Se non si dispone di una topologia ibrida di Skype for business stabilita, è necessario farlo per abilitare una migrazione agevole degli utenti della segreteria telefonica. Per ulteriori informazioni, vedere [Configurare Skype for business Hybrid](../../SfbHybrid/hybrid/configure-federation-with-skype-for-business-online.md) . 

    > [!Note]
    > Non è necessario eseguire la migrazione degli utenti in linea per la migrazione del servizio segreteria telefonica. Tuttavia, per gli utenti locali per sfruttare il servizio segreteria telefonica del sistema telefonico, è necessario stabilire una topologia ibrida.

3. **Pianificare la migrazione dell'operatore automatico**
    
    Gli amministratori possono avviare la migrazione degli operatori automatici da ExchUMO all'operatore automatico cloud in qualsiasi momento. Per ulteriori informazioni, vedere [configurare un operatore automatico cloud](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant) . Microsoft continua a fornire ulteriori funzionalità di operatore automatico che i clienti possono prendere in considerazione per la migrazione, gli amministratori devono valutare il set di caratteristiche e migrare le istanze dell'operatore automatico di conseguenza. Per il confronto tra gli elenchi di funzionalità, vedere la [matrice di caratteristiche dei servizi basati su cloud di ExchUMO e Azure](#exchumo-and-azure-cloud-based-services-feature-matrix).

4. **Pianificare la convalida e il testing di post-migrazione della segreteria telefonica**

    La migrazione della segreteria telefonica è basata su Microsoft. Gli amministratori non sono tenuti a eseguire alcuna operazione, a condizione che sia stata stabilita la topologia ibrida prerequisita. Microsoft esegue la convalida e il testing necessari per assicurarsi che la migrazione della segreteria telefonica degli utenti non venga interrotta. Gli amministratori sono invitati a eseguire il testing e la convalida dalla propria parte. Vedere il [piano di testing suggerito e la convalida dopo la migrazione per gli amministratori](#suggested-test-plan-and-post-migration-validation-for-admins) per un piano di testing consigliato. 

    > [!Note]
    > Lync Server 2010 non è supportato. Se si è in una distribuzione di 2010 Server, è consigliabile pianificare l'aggiornamento di un server o considerare la possibilità di migrare gli utenti a Microsoft teams o Skype for business online.  

5. **Monitorare il centro notifiche di amministrazione**

    Consultare una notifica nel centro notifiche di amministrazione con ulteriori dettagli e sequenza temporale sulla migrazione degli utenti. Le notifiche vengono inviate almeno 30 giorni prima del periodo di migrazione. 

    > [!Note]
    > Se è stata ricevuta una notifica con la sequenza temporale della migrazione degli utenti e si desidera posticipare la migrazione per motivi aziendali, è possibile contattare il supporto tecnico Microsoft. Si noti che non è possibile posticipare la migrazione oltre la data di pensionamento, il 28 febbraio 2020. Per i clienti che potrebbero avere altre domande, contattare il team account o il supporto tecnico Microsoft. I clienti che già utilizzano Office 365 possono inviare un caso di supporto tramite l'interfaccia di amministrazione di Microsoft 365. 

6. **Considerare la possibilità di optare per una migrazione pianificata**

    È possibile optare per una migrazione del servizio di segreteria telefonica pianificata a CVM. Prima di procedere con la scelta, esaminare i dettagli di questo articolo, in particolare le sezioni seguenti:

    - Passaggi di migrazione (questa sezione)
    - Matrice delle funzionalità dei servizi basati su cloud di ExchUMO e Azure
    - Impatto sull'esperienza utente

    Quando si sceglie una migrazione gestita, non si riceverà una notifica di 30 giorni prima della migrazione nel centro messaggi del portale di amministrazione di Microsoft 365.
 
    Per optare per una migrazione pianificata, inviare una richiesta di posta elettronica dall'indirizzo di posta elettronica dell'amministratore a [CVM@microsoft.com](mailto:cvm@microsoft.com) con le seguenti informazioni:

    - Data preferita (martedì): le ondate di migrazione vengono eseguite ogni martedì. Selezionare una data di martedì che non superi i 12/3/2019.
 
    - ID tenant: 32 caratteri numerici in questo formato 0046728c-688a-4472-a38f-098fec60ac6x. È possibile trovare l'ID tenant nel portale di amministrazione di Microsoft 365 in Azure AD o utilizzando il cmdlet di PowerShell seguente:`Get-CsTenant | Select ObjectId`
 
    Una volta che il tenant ha eseguito la migrazione, viene ricevuta una conferma tramite posta elettronica.

## <a name="auto-attendant-migration-guidelines"></a>Linee guida per la migrazione degli operatori automatici

Gli amministratori dell'organizzazione di Office 365 sono tenuti a ricreare gli operatori automatici di messaggistica unificata di Exchange nel servizio Microsoft Cloud AutoAttendant e a scambiarli con i numeri di telefono locali prima del 28 febbraio 2020, ovvero quando il servizio UMO di Exchange verrà ritirato. Questa è la linea guida consigliata per eseguire correttamente la migrazione e testare nuovi operatori automatici cloud. Se si dispone di un numero elevato di operatori automatici, è possibile utilizzare l' [operatore automatico di messaggistica unificata di Exchange per gli script di migrazione degli operatori](https://github.com/NathanJBennett/ExUMAAMigrationToCloudAA) automatici del cloud per semplificare la migrazione in blocco degli operatori automatici.

### <a name="setup"></a>Configurazione

È consigliabile avviare la configurazione dei nuovi operatori automatici per evitare problemi relativi all'ultimo minuto e acquisire familiarità con la funzionalità e l'esperienza del servizio operatore automatico cloud. Per gli operatori automatici che richiedono una o più funzionalità di Gap, è possibile creare e testare gli operatori automatici quando le funzionalità Gap sono disponibili per prepararsi per la distribuzione. Per ulteriori informazioni sulle funzionalità Gap, vedere l' [appendice](#appendix).

1. Utilizzare i cmdlet di UMO di Exchange per esportare la configurazione degli operatori automatici esistenti utilizzando [Get-UMAutoAttendant](https://docs.microsoft.com/powershell/module/exchange/unified-messaging/get-umautoattendant).  
2. Utilizzare il cmdlet [Export-UMprompt](https://docs.microsoft.com/powershell/module/exchange/unified-messaging/export-umprompt) in Exchange Online PowerShell per esportare i file multimediali di saluto (se usati) e convertirli in formato. mp3.
3. Seguire le istruzioni riportate in [Plan cloud auto attendants](../../SfbHybrid/hybrid/plan-cloud-auto-attendant.md) e [configurare un operatore automatico cloud](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant) per creare operatori automatici utilizzando l'interfaccia di amministrazione di Microsoft teams o PowerShell.
4. Esaminare i messaggi di saluto se le opzioni di menu sono state modificate.
5. Configurare i trasferimenti ai Response Group utilizzando la soluzione "trasferimento automatico chiamata al servizio PSTN" nella sezione [problemi noti](#known-issues) di questo articolo.  
6. Testare i nuovi operatori automatici. Per eseguire il test, chiamarli internamente o assegnare un numero di telefono di prova.  

### <a name="cutover"></a>Completa

1. Passare i numeri di telefono dagli operatori automatici di Exchange UMO ai nuovi operatori automatici.
2. Spostare l'URI SIP dall'oggetto contatto nell'account della risorsa.
3. Testare e convalidare gli operatori automatici utilizzando i numeri di telefono appena assegnati. 

## <a name="appendix"></a>Appendice

### <a name="exchumo-and-azure-cloud-based-services-feature-matrix"></a>Matrice delle funzionalità dei servizi basati su cloud di ExchUMO e Azure

| Servizio | Livello di funzionalità | Funzionalità | Notes  | Cloud VM/AA  | ExUMO |
|---------|-------|--------|----|--------|------|
| VM  | Funzionalità del servizio| Supporto del sistema PBX di terze parti    | Inclusione di tutte le funzionalità fornite a PBX di terze parti, ad esempio MWI (indicatore di messaggio in attesa) tramite messaggi SIP NOTIFY dalla messaggistica unificata di Exchange Online | N   | Y    |
| VM | Funzionalità del servizio  | Supporto di Skype for Business Server   |  | Y | Y    |
| VM | Funzionalità del servizio | Supporto di Microsoft Teams|  | Y | N    |
| VM | Funzionalità del servizio | eDiscovery e blocco  | Per la sicurezza e la conformità  | Y | Y    |
| VM | Funzionalità del servizio | Supporto delle regole di Exchange | Per la sicurezza e la conformità  | Y | Y    |
| VM | Funzionalità utente | Accesso esterno PSTN  | Accesso sottoscrittore  | N | Y    |
| VM | Funzionalità utente | PSTN Outlook Voice Access   | Accesso sottoscrittore  | N | Y    |
| VM | Funzionalità utente | Accesso esterno tramite un endpoint autenticato | Chiamata del servizio segreteria telefonica per l'ascolto dei messaggi vocali e la modifica delle impostazioni della segreteria telefonica| Y | Y    |
| VM | Funzionalità utente | Impostazione utente per disabilitare la segreteria telefonica   |  | Y | Y    |
| VM | Funzionalità utente | Impostazione utente per modificare il messaggio di saluto personale  |  | Y | Y    |
| VM | Funzionalità utente | Impostazione utente per creare un messaggio di saluto fuori sede  |  | Y | Y    |
| VM | Funzionalità utente | Impostazione utente per modificare la lingua predefinita  |  | Y | Y    |
| VM | Funzionalità utente | Impostazione utente per sovrascrivere il messaggio di saluto predefinito con TTS  |  | Y | N    |
| VM | Funzionalità utente | Registrare messaggi di saluto personali (dispositivo autenticato) |  | Y | Y    |
| VM | Funzionalità utente | Registrare messaggi di saluto personali (PSTN): Ascolta al telefono |  | N | Y    |
| VM | Funzionalità utente | Impostazione utente per disabilitare la trascrizione |  | N | Y    |
| VM | Funzionalità utente | Trascrizione  |  | Y | Y    |
| VM | Funzionalità utente | Segreteria telefonica visiva su tutti gli endpoint   | Con controllo utente da riprodurre, eliminare, indicatore di messaggio in attesa e stato-Toggle, in tutti gli endpoint supportati  | Y | Y    |
| VM | Funzionalità utente | Formato di file audio MP3 in Outlook    |  | Y | Y    |
| VM | Funzionalità utente | Controllo velocità di riproduzione variabile |  | Y | Y    |
| VM | Funzionalità utente | Inoltrare una segreteria telefonica  | Inoltrare una segreteria telefonica ricevuta ad altri utenti | Y | Y    |
| VM | Funzionalità utente | Invio di un messaggio vocale a un gruppo di utenti  |Trasmissione della segreteria telefonica   | N | Y   |
| VM | Funzionalità utente | Notifica della segreteria telefonica tramite SMS    | Gli utenti possono ricevere un SMS quando hanno una nuova segreteria telefonica    | N | Y    |
| VM | Funzionalità utente | Lingue di saluto supportate | Informazioni dettagliate:https://docs.microsoft.com/microsoftteams/what-are-phone-system-auto-attendants | Y | Y    |
| VM | Funzionalità utente | Regole di ricezione chiamata |  | Y | Y    |
| VM | Funzionalità utente | Ascolta al telefono (PSTN)-per riprodurre il messaggio | Chiamami sul mio cellulare per ascoltare il messaggio vocale  | N | Y    |
| VM | Funzionalità utente | Ascolta al telefono (auth)-per riprodurre il messaggio | Chiamami sul dispositivo autenticato  | Y | Y    |
| VM | Funzionalità utente | Cassetta postale condivisa tra più utenti |  | Y | Y    |
| VM | Funzionalità del chiamante  | Esperienza chiamante: protezione della segreteria telefonica | Il chiamante può scegliere un'opzione per contrassegnare un messaggio registrato come protetto| N | Y    |
| VM | Funzionalità del chiamante  | Esperienza chiamante-segreteria telefonica privata | Il chiamante può scegliere un'opzione per contrassegnare un messaggio registrato come privato  | N | Y    |
| VM | Funzionalità del chiamante  | Rilevamento del silenzio   |  | N | Y    |
| VM | Funzionalità tenant-admin | Segreteria telefonica protetta a livello di server    | Tenant-admin può configurare una regola a livello di servizio per contrassegnare la segreteria telefonica in arrivo come protetta | Y | Y    |
| VM | Funzionalità tenant-admin | Modificare la durata del periodo di registrazione  |     | Y | Y    |
| VM | Funzionalità tenant-admin | Modificare il timeout di rilevamento del silenzio    |  | N/D    | Y    |
| VM | Funzionalità tenant-admin | Modificare il numero di errori di input | CVM: hardcoded su 3 | N | Y    |
| VM | Funzionalità tenant-admin | Modificare la lingua predefinita |  | Y | Y    |
| VM | Funzionalità tenant-admin | Disabilitazione/abilitazione della trascrizione |  | Y | Y    |
| VM | Funzionalità tenant-admin | Disabilitare/attivare la notifica di chiamata senza risposta |  | N | Y    |
| VM | Funzionalità tenant-admin | Consenti a Microsoft di migliorare l'anteprima della casella vocale    |  | Y | Y    |
| VM | Funzionalità tenant-admin | Personalizzazione del messaggio di testo per gli utenti abilitati|  | N/D    | Y    |
| VM | Funzionalità tenant-admin | Trascrizione mascheramento parolacce|  | Y | N    |
| VM | Funzionalità tenant-admin | Criteri di segreteria telefonica    |   | Y | Y    |
| VM | Funzionalità tenant-admin | Amministrazione portale Web   |  | CY19   | Y    |
| VM | Funzionalità tenant-admin | PowerShell   |  | Y | Y    |
| AA | Funzionalità del servizio | Supporto di terze parti PBX di AA    |  | N | Y    |
| AA | Funzionalità del servizio | Supporto di Skype for Business Server   |  | Y | Y    |
| AA | Funzionalità del servizio | Supporto di Microsoft Teams|  | Y | N    |
| AA | Funzionalità del servizio | Composizione per nome, input DTMF    |  | Y | Y    |
| AA | Funzionalità del servizio | Composizione per nome, input vocale  |  | Y | Y    |
| AA | Funzionalità del servizio | Supporto multilingue | Informazioni dettagliate sulla lingua:https://docs.microsoft.com/microsoftteams/what-are-phone-system-auto-attendants | Y | Y    |
| AA | Funzionalità del servizio | Trasferimento all'operatore, al CQ o a un utente |  | Y | Y    |
| AA | Funzionalità del servizio | Trasferimento al numero PSTN internamente (DID inversa)  |  | Y | Y    |
| AA | Funzionalità del servizio | Trasferimento al numero PSTN esternamente  |  | Vedere la sezione problemi noti riportati di seguito | Y    |
| AA | Funzionalità del servizio | Ore lavorative |  | Y | Y    |
| AA | Funzionalità del servizio | Opzioni di menu | Opzioni di menu IVR  | Y | Y    |
| AA | Funzionalità del servizio | Assegnazione di un numero PSTN cloud a AA |  | Y | N    |
| AA | Funzionalità del servizio | Assegnazione di un numero PSTN su AA  |  | Y | Y    |
| AA | Funzionalità del servizio | Selezione personalizzata degli utenti  | Consentire ai chiamanti di raggiungere un elenco personalizzato di utenti dell'organizzazione| Y | Y    |
| AA | Funzionalità del servizio | Trattamento after-hours and Holidays  |  | Y | Y    |
| AA | Funzionalità del servizio | Messaggio di saluto personalizzato utilizzando il testo per la sintesi vocale  |  | Y | Y    |
| AA | Funzionalità del servizio | Composizione estensione   | Raggiungimento di un utente mediante composizione dell'estensione  | Y   | Y    |
| AA | Funzionalità del servizio | Cassetta postale per i chiamanti AA per lasciare un messaggio    |  | Y   | Y    |
| AA | Funzionalità del servizio | Più assegnazioni di numeri PSTN a un AA|  | Y | Y    |
| AA | Funzionalità tenant-admin | Amministrazione portale Web   |  | Y | N    |
| AA | Funzionalità tenant-admin | Cmdlet di PowerShell  |  | Y | Y    |
| Fax| Funzionalità del servizio | Integrazione fax|  | N | Y    |

### <a name="suggested-test-plan-and-post-migration-validation-for-admins"></a>Piano di testing suggerito e convalida dopo la migrazione per gli amministratori

Per convalidare la migrazione degli utenti alla segreteria telefonica cloud, lasciare una segreteria telefonica a un utente e controllare il corpo del messaggio in Outlook.  I messaggi di segreteria telefonica cloud dispongono di un piè di pagina che legge:

**La ringrazio per l'utilizzo della trascrizione. Se non si vede una trascrizione sopra, è perché la qualità audio non è abbastanza chiaro per trascrivere.**

Quando si verifica la funzionalità della segreteria telefonica dopo la migrazione degli utenti, prendere in considerazione gli scenari seguenti:

- Convalidare l'accesso alla segreteria telefonica su tutti i tipi di endpoint nell'organizzazione: app e telefoni IP. 
- Convalidare con gli utenti di esempio che i messaggi di saluto personalizzati configurati vengono riprodotti ai chiamanti.   
- Se l'organizzazione ha un requisito legale o di conformità per disabilitare la trascrizione per gli utenti, assicurarsi che sia disabilitata dopo la migrazione. Per ulteriori informazioni, vedere [set up cloud Voicemail](/microsoftteams/set-up-phone-system-voicemail).
- Se sono stati precedentemente configurati i criteri e le regole della VM di Exchange, verificare che siano efficaci.
- Acquisire familiarità con i cmdlet di PowerShell per i servizi di segreteria cloud per modificare le impostazioni dell'utente.  

### <a name="user-experience-impact"></a>Impatto sull'esperienza utente

Di seguito è riportata una panoramica dell'esperienza di migrazione della segreteria telefonica per gli utenti finali.


|Funzionalità  |Modifica dell'esperienza utente|
|---------|---------|
|Notifica tramite posta elettronica | Nessuna modifica<br>Non viene inviato alcun messaggio di posta elettronica agli utenti che li notificano sull'attivazione/migrazione degli account vocali. |
|Accesso ai messaggi precedenti | Nessuna modifica<br>Gli utenti hanno accesso ai messaggi vocali precedenti in tutti gli endpoint supportati. |
|Ricezione di macchine virtuali in Outlook, app di questo| Nessuna modifica<br>Gli utenti continuano a ricevere i messaggi vocali in tutti gli endpoint supportati. |
|Trascrizione | Avanzato<br>La trascrizione di CVM ha un tasso di precisione molto più elevato e lingue supportate rispetto a ExchUMO. |
|Impostazione utente | Nuova esperienza<br>Gli utenti sono in grado di modificare le proprie preferenze da un portale di impostazioni utente (USP). Gli utenti possono accedere al proprio USP da un collegamento ipertestuale nella posta elettronica della segreteria telefonica oppure il pulsante Impostazioni utente nel proprio client di questo. https://aka.ms/vmsettings.   
 |Funzionalità| Per informazioni dettagliate, vedere il confronto tra set di caratteristiche. |
|Regole di Outlook per i messaggi VM | Nessuna modifica<br>Le regole create in precedenza si applicheranno ai messaggi di CVM dopo la migrazione.
 |

#### <a name="user-management-and-provisioning-in-cvm"></a>Gestione e provisioning degli utenti in CVM

I nuovi utenti di Skype for business verranno automaticamente provisionati per la segreteria telefonica cloud quando vengono creati. Per il provisioning di nuovi utenti di segreteria telefonica non è necessaria alcuna licenza o lavoro aggiuntivo. Per ulteriori informazioni sulla gestione dei criteri per gli utenti esistenti e nuovi, vedere [set up cloud Voicemail](/microsoftteams/set-up-phone-system-voicemail) .

#### <a name="admin-auto-attendant-management-experience"></a>Esperienza di gestione dell'operatore automatico di amministrazione

Per ulteriori informazioni sugli operatori automatici, vedere [configurare un operatore automatico cloud](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant).

#### <a name="known-issues"></a>Problemi noti

**Disabilitare l'accesso sottoscrittore dopo la migrazione per evitare l'incoerenza del messaggio** L'accesso sottoscrittore potrebbe continuare a funzionare per il tenant fino a quando il servizio è completamente ritirato, anche dopo che tutti gli utenti sono stati migrati nella segreteria telefonica cloud. Per evitare confusione tra gli utenti e un'esperienza incoerente, disabilitare l'accesso sottoscrittore dopo che i messaggi di saluto sono stati modificati dopo che la migrazione non avrà alcun effetto. A tale scopo, rimuovere il contatto EXUM per ogni riga di accesso del Sottoscrittore tramite Get-CsExUmContact |? {$_. IsSubscriberAccess vengono impostate-eq $true} | Remove-CsExUmContact 

**Trasferimento di chiamata dell'operatore automatico a PSTN** I clienti sono invitati a configurare temporaneamente una soluzione per soddisfare i requisiti per il trasferimento di una chiamata all'operatore automatico a un numero PSTN esterno o a un'istanza di RGS. 
 
Un problema è stato identificato durante la garanzia della qualità con la caratteristica di trasferimento alla funzionalità dei numeri PSTN, che non verrà risolta in tempo per i clienti per iniziare la migrazione dal servizio UMO di Exchange prima della data di pensionamento pianificata del 28 febbraio 2020. Come soluzione alternativa, gli amministratori possono trasferire i chiamanti dell'operatore automatico a un utente virtuale locale con un'impostazione di inoltro di chiamata attiva per il numero di telefono PSTN desiderato o il numero di telefono RGS. 
 
Esperienza prevista
- Gli amministratori non hanno la necessità di concedere una licenza all'utente virtuale, poiché si tratta di una soluzione alternativa 
- Gli amministratori possono modificare l'ID chiamante che il ricevitore PSTN vedrà assegnando il numero desiderato all'utente virtuale oppure utilizzando le funzionalità di manipolazione delle cifre SBC
- I chiamanti PSTN non avranno ritardi durante il trasferimento di chiamata e continueranno a visualizzare l'ID chiamante dell'operatore automatico dopo che il trasferimento ha avuto esito positivo  

**Cassetta postale condivisa:** Una cassetta postale condivisa configurata utilizzando la messaggistica unificata di Exchange Online continuerà a ricevere i messaggi dopo la migrazione a CVM e continuerà a essere accessibile agli utenti tramite Outlook. Tuttavia, l'accesso alla modifica dei messaggi di saluto di queste cassette postali non sarà disponibile dopo la migrazione a CVM. I clienti con cassette postali condivise utilizzate per acquisire i chiamanti dell'operatore automatico devono sfruttare gli operatori automatici e le funzionalità delle cassette postali condivise delle code di chiamata, una volta rilasciate (ETA ottobre 2019).
  
**Eseguire l'aggiornamento a banner di teams sul client di questo:** Il servizio CVM si basa sull'infrastruttura di Microsoft teams. le chiamate effettuate dal client Skype for business possono provocare la visualizzazione di un banner informativo sul client in cui si legge: "nomeutente non utilizza Skype for business. Per un'esperienza più completa, passare a teams o avviare una riunione Skype.
Assicurarsi di aggiornare il client Skype for business degli utenti all'ultimo aggiornamento client di C2R per evitare che questo banner venga visualizzato.
  
**Setup la segreteria telefonica vi porterà a OWA:** Facendo clic su "Configura segreteria telefonica" dal client continuerà a prendere Skype for Business Server 2015/2013 clienti alla pagina del portale di Office Web Access (OWA) dopo la migrazione a CVM. Tutte le impostazioni sono state rimosse dalla scheda segreteria telefonica in OWA e un banner verrà visualizzato con un collegamento di reindirizzamento per consentire agli utenti di utilizzare il portale delle impostazioni utente di CVM.
 
**Modificare Greeting Mobile Access:** L'accesso sottoscrittore PSTN non è supportato in CVM. Per gli utenti che hanno la necessità di modificare il proprio messaggio di saluto in remoto, viene aggiunta un'opzione di menu "cambia il messaggio di saluto" alla segreteria telefonica IVR per i client mobili. Gli utenti possono chiamare questo servizio premendo e tenendo premuto il tasto "1" nel dial-pad del client per dispositivi mobili.
