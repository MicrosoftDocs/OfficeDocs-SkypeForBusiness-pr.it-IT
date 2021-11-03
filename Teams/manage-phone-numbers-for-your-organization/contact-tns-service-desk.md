---
title: Contattare il team dei servizi di numeri di telefono
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: conceptual
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.voice.tnsservicedesk
- ms.teamsadmincenter.voice.contacttnssupport
- Calling Plans
ROBOTS: NOINDEX, NOFOLLOW
description: Quando si ottengono numeri di telefono o numeri di porta (trasferimento) per l'organizzazione, potrebbe essere necessario ottenere assistenza e supporto presso il service desk TNS.
ms.openlocfilehash: c32a6ed98cc54d04783025eacd03cb178e7f9120
ms.sourcegitcommit: bf350ea47032bd926e75a5433eadce3905e731ca
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2021
ms.locfileid: "60733870"
---
# <a name="telephone-number-services-tns---service-desk"></a>Telephone Number Services (TNS) - Service Desk 

Esiste un nuovo processo per interagire con il service desk TNS (Telephone Number Services). È ora possibile aprire i ticket, visualizzare i ticket e tenere traccia delle comunicazioni in un'unica posizione integrata con l'interfaccia di amministrazione di Teams. Questo articolo descrive tutto ciò che è necessario sapere per contattare il service desk.

> [!NOTE]
> A partire dal 22 luglio 2021, il sistema di posta elettronica corrente è stato ritirato.

Per contattare il supporto tecnico:

1. Accedere all'interfaccia di amministrazione di Teams - admin.teams.microsoft.com.

2. Nel riquadro sinistro selezionare **Numeri di telefono**.

3. Nella parte superiore della pagina selezionare **Ottenere il supporto per il numero di telefono**. Verrà visualizzato il Centro assistenza numeri di telefono.  

> [!NOTE]
> Solo un utente dello stesso tenant potrà creare un caso. Ovvero, un utente di @fabrikam.com non può creare un caso per conto di @contoso.com. 

Dal Centro assistenza numeri di telefono è possibile creare nuovi casi, visualizzare casi esistenti, comunicare con il service desk e gestire il profilo utente. Ogni area è descritta in modo dettagliato nelle sezioni seguenti.

- **Il Centro assistenza numeri di telefono** – Passare al portale home page. 

- **[Creare un nuovo caso](#create-a-new-case)** – inviare una nuova richiesta o un'istruzione generale. 

- **[Visualizzare i casi esistenti](#view-and-manage-existing-cases)**– Tenere traccia e monitorare i casi esistenti. 

- **[Visualizzare i casi aziendali](#view-and-manage-existing-cases)** – Tenere traccia e monitorare i ’ casi esistenti dell'azienda. Se i colleghi dell'azienda hanno aperto casi, è possibile cercarli in questa visualizzazione.  

- **[Inviare un feedback](#view-and-manage-existing-cases)**–Potete condividere facilmente il vostro feedback. 

- **[Nome]** Aggiornare la – pagina del profilo. 

## <a name="create-a-new-case"></a>Creare un nuovo caso

Per creare un nuovo caso, seguire questa procedura:

1. Selezionare **Creare un nuovo caso** da una delle posizioni seguenti:  

   - Nella pagina **Centro assistenza numeri di telefono**, nella parte superiore della pagina o nel riquadro inferiore.

   - Nella pagina **Visualizza i casi esistenti**.

   - Nella pagina **Visualizza casi aziendali**.

2. Specificare i dettagli del caso come descritto in dettaglio nella sezione[ successiva](#provide-case-details).

3. Dopo aver immesso tutti i valori, selezionare **Invia**. Verrà visualizzata una nuova schermata in cui è possibile visualizzare il numero del caso.  

### <a name="provide-case-details"></a>Specificare i dettagli del caso

Per comprendere i dettagli del caso, Microsoft necessita delle informazioni seguenti:

- [Categoria del caso](#case-category)
- [Paese o area geografica](#country-or-region)
- [Tipologia di caso](#case-type)
- [Titolo del caso](#case-title)
- [Contatti aggiuntivi per le notifiche](#additional-contacts-for-notifications)
- [Descrizione](#description)
- [Ulteriori documenti di supporto](#additional-supporting-documents)

#### <a name="case-category"></a>Categoria del caso

Un caso può avere una delle due categorie seguenti: 

- **Inviare una nuova richiesta**- Scegliere questa opzione se si vuole inviare una nuova richiesta. Ad esempio, si vuole inviare una richiesta di porta o acquistare numeri di telefono da Microsoft.  

- **Richiesta generale**- Scegliere questa opzione se si hanno domande utili per determinare la richiesta. Ad esempio, è necessario sapere se è possibile trasferire i numeri wireless a Microsoft o se Microsoft supporta numeri verdi vanity. 

#### <a name="country-or-region"></a>Paese o area geografica

Selezionare il paese/area geografica per cui si sta inviando il caso. Se si hanno richieste per più paesi, è necessario aprire un caso per paese/area geografica.  

#### <a name="case-type"></a>Tipo di caso

Il tipo di caso può essere uno dei seguenti:

- **Nome di chiamata personalizzato (solo STATI UNITI)** - Impostare un nome di chiamata personalizzato sui numeri di telefono Microsoft. Questa opzione è applicabile solo ai numeri di telefono degli Stati Uniti. 

  - **Nome di chiamata personalizzato da impostare (solo 15 caratteri)** - Il nome di chiamata personalizzato che si desidera impostare. Il nome ha un limite massimo di 15 caratteri.  

  - **Elenco dei numeri di telefono** - Elenco di numeri di telefono per cui si vuole impostare un valore del nome di chiamata personalizzato. Caricare un file CSV con l'elenco dei numeri di telefono.  

- **Porta del tenant Inter**– Spostare i numeri di telefono da un tenant a un altro. Ad esempio, si hanno due tenant diversi all'interno di Microsoft e si vogliono spostare i numeri di telefono da un tenant all'altro.  

  - **Nome di dominio del tenant di origine** - Il tenant da cui si vogliono spostare i numeri di telefono in un tenant diverso.  

  - **Identificatore univoco del tenant di origine** - ID del tenant per il tenant di origine. Questo è un campo facoltativo.  

  - **Nome di dominio del tenant di destinazione** - Il tenant in cui si vogliono spostare i numeri di telefono.  

  - **Identificatore univoco del tenant di destinazione** - ID tenant per il tenant di destinazione. Questo è un campo facoltativo.  

  - **Data/ora richiesta*** - Data e ora in cui spostare i numeri dal tenant di origine al tenant di destinazione. Vedere Data e ora.

  - **Elenco dei numeri di telefono** - Elenco dei numeri di telefono che si desidera spostare dal tenant di origine al tenant di destinazione. Caricare un file CSV con l'elenco dei numeri di telefono. 

- **Modifica del tipo di inventario**– Modificare il tipo di numeri di telefono. Ad esempio, si desidera modificare i numeri di abbonamento Microsoft in numeri di servizio. Per altre informazioni sui tipi di numeri di telefono supportati da Microsoft, vedere [Tipi di numeri di telefono](../different-kinds-of-phone-numbers-used-for-calling-plans.md).

  - **Converti in** - Selezionare questa opzione per convertire i numeri in numeri utente o in numeri di servizio. 

  - **Datetime preferito*** - Data e ora in cui si vuole modificare il tipo di inventario dei numeri. Per altre informazioni, vedere Data e ora.

  - **Casella di verifica - Sono consapevole che per poter aggiornare il tipo di inventario, i miei numeri di – telefono devono essere non assegnati** - Microsoft non può elaborare le richieste di modifica del tipo di numero di telefono a meno che i numeri di telefono all'interno del tenant non siano assegnati. Se si richiede questa modifica per una data futura, sarà necessario assicurarsi che i numeri non siano assegnati prima della data e dell'ora richieste. 

  - **Elenco dei numeri di telefono** - L'elenco dei numeri di telefono di cui si vuole modificare il tipo. Caricare un file CSV con l'elenco dei numeri di telefono. 

- **Nuova acquisizione TN**– Acquistare nuovi numeri di telefono da Microsoft.  

  - **Tipo di numero** - Selezionare il tipo per i numeri. Vedere [Tipi di numeri di telefono](../different-kinds-of-phone-numbers-used-for-calling-plans.md).

  - **Hai provato a ottenere i numeri di telefono dal portale dell'interfaccia di amministrazione di Teams** - Hai provato ad acquistare questi numeri di telefono dal portale dell'interfaccia di amministrazione di Microsoft Teams, dove puoi usare la funzionalità self-service?  

  - **Quantità di numeri di telefono necessari** - Il calcolo di numeri di telefono da acquistare.  

  - **Stato/provincia** - Stato/provincia all'interno del paese/area geografica per cui si vogliono i numeri di telefono.  

  - **Città** - Città all'interno dello stato o della provincia per cui si vogliono i numeri di telefono.  

  - **Indirizzo di Office** - E’ specifico solo per determinati paesi. Questo è l'indirizzo del sito di Office.  

  - **Directory** - Specifica solo per determinati paesi. Vuoi pubblicare le informazioni aziendali con i numeri di telefono?  

- **Portabilità**– Porta numeri di telefono esistenti dal provider di servizi corrente a Microsoft.  

  - **Assegnare un nome all'ordine di portabilità** - specificare un nome facile da ricordare per la richiesta di portabilità. 

  -  **Data/ora di portabilità richiesta*** - Data e ora in cui si desidera trasferire i numeri a Microsoft. Si noti che non si tratta di una data di portabilità garantita, poiché il proprietario del numero corrente deve prima approvare la richiesta di portabilità. Vedere Data e ora. 

  - **Elenco dei numeri di portabilità** - Elenco dei numeri di telefono da convertire in Microsoft. Caricare un file CSV con l'elenco dei numeri di telefono. 

  - **Lettera di autorizzazione (LOA)** : allegare qui una lettera di autorizzazione firmata e compilata. Microsoft non può elaborare una richiesta di portabilità senza una lettera di autorizzazione..  

- **Aggiornamento indirizzo**– Aggiornare l'indirizzo per le chiamate di emergenza. Si noti che questo campo si applica solo a determinati paesi. 

  - **Posizione ID** - ID posizione per l'indirizzo di emergenza. 

  - **Elenco dei numeri di telefono** - Elenco dei numeri di telefono per cui si vuole modificare l'indirizzo di emergenza (immettere l'indirizzo desiderato nel campo Descrizione). Caricare un file CSV con l'elenco dei numeri di telefono. 

***Data e ora.** Se si seleziona Paese = Francia, data = 14/8/2021 e ora = 10:00, la richiesta verrà eseguita il 14/8/2021 alle 10:00. Ora francese. 

#### <a name="case-title"></a>Titolo del caso

Immettere un titolo che riepiloga la richiesta.  

#### <a name="additional-contacts-for-notifications"></a>Contatti aggiuntivi per le notifiche

Immetti l'elenco delle persone che riceveranno notifiche automatiche sullo stato da Microsoft. Ad esempio, si vuole inserire un ordine di conversione e si vuole che altri due colleghi, oltre a se stessi, ricevano notifiche di stato automatizzate. Specificare gli indirizzi di posta elettronica dei colleghi nella sezione **Messaggi di posta elettronica di notifica**. Questa impostazione è facoltativa. 

#### <a name="description"></a>Descrizione

Descrivi cosa stai cercando di ottenere ed elenca le tue domande per il service desk Microsoft Telephone Number Services (TNS).  

#### <a name="additional-supporting-documents"></a>Ulteriori documenti di supporto

Caricare eventuali documenti aggiuntivi per il caso.  

## <a name="view-and-manage-existing-cases"></a>Visualizzare e gestire i casi esistenti

È possibile visualizzare i casi selezionando **Visualizza i casi esistenti** e selezionando il numero del caso. Se si seleziona un numero di caso, si verrà reindirizzati ai dettagli del caso. È anche possibile visualizzare i casi aziendali selezionando **Visualizza casi aziendali**.  È anche possibile:

- **Filtrare i casi** selezionando **Casi aperti**,  **Tutti i casi** o **Casi chiusi**.

- **Comunicare con il service desk TNS** per quanto riguarda il caso aprendo un caso esistente, scorrendo verso il basso e selezionando **Aggiungi commento.** Verrà visualizzata una nuova finestra. Immettere il messaggio nella casella del commento. Allegare tutti i documenti di supporto (se disponibili) che potrebbero essere utili per la richiesta e selezionare **Invia**.  

  Le risposte del **service desk TNS** verranno visualizzate sotto la stessa sequenza temporale. Quando viene eseguito un aggiornamento del caso, si riceverà una notifica automatica tramite posta elettronica dell'aggiornamento. 

- **Annullare un** caso passando a un caso esistente, scorrendo verso il basso e selezionando **Annulla caso.** Selezionare un motivo per l'annullamento dall'elenco a discesa, quindi selezionare **Annulla**.  

- **Risolvere un caso** : se si ritiene che la richiesta sia stata completata, è possibile risolvere un caso passando a un caso esistente, scorrendo verso il basso e selezionando **Risolvi caso**. Selezionare **Chiudi**; il caso verrà ora visualizzato come **Risolto- Problema risolto**.  


## <a name="related-topics-and-additional-resources"></a>Argomenti correlati e risorse aggiuntive

- Per assistenza relativa alla configurazione e alla configurazione dei numeri, alle licenze, alle tariffe o alla fatturazione, vedere [Contatto di supporto per i prodotti aziendali - Guida per l'amministratore](/microsoft-365/admin/contact-support-for-business-products?tabs=online&view=o365-worldwide).

- Per sapere se l'audioconferenza è disponibile nel paese/area geografica di interesse, vedere [Disponibilità di Audioconferenza e Piani per chiamate per Paese e area geografica](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).

- Per informazioni utili per selezionare i tipi appropriati di numeri di telefono per l'organizzazione, vedere [diversi tipi di numeri di telefono](../different-kinds-of-phone-numbers-used-for-calling-plans.md).

- Per informazioni sulla gestione dei numeri di telefono per l'organizzazione, vedere [Gestire i numeri di telefono per l'organizzazione](manage-phone-numbers-for-your-organization.md).

- Per informazioni sui termini e le condizioni per le chiamate di emergenza, vedere [termini e condizioni per le chiamate di emergenza](../emergency-calling-terms-and-conditions.md).
