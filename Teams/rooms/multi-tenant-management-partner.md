---
title: Gestione clienti multi-tenant per partner
author: donnah007
ms.author: v-donnahill
ms.date: 07/25/2022
manager: serdars
ms.reviewer: dstrome
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Gestione clienti Mult-tenant per partner.
f1keywords: ''
ms.openlocfilehash: 23b0460d5f59830ea00522ac001b7f7524ad2f45
ms.sourcegitcommit: 3266fde54b92a18865d666b98e4e7e8322b9dedc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/26/2022
ms.locfileid: "67024119"
---
# <a name="multi-tenant-customer-management-for-partners"></a>Gestione clienti multi-tenant per partner

La gestione multi-tenant (MTM) nel servizio Teams Rooms Managed (TRM) consente alle organizzazioni partner di gestire più clienti in un'unica posizione, con le proprie credenziali di dominio. Gli utenti partner vedranno solo le chat room dei clienti a cui sono assegnate. È possibile applicare ruoli personalizzati per ogni cliente nel tenant MTM, offrendo alle organizzazioni partner un controllo granulare delle autorizzazioni per le risorse del cliente. 

Il portale MTM è accessibile tramite questo [collegamento](https://partner.rooms.microsoft.com/).

> [!Note] 
> Le organizzazioni partner non possono gestire le proprie chat room tramite il portale MTM. Queste chat room possono essere gestite nel [portale TRM](https://portal.rooms.microsoft.com/). 

## <a name="pre-requisites-for-managing-your-customers-through-the-mtm-experience"></a>Prerequisiti per la gestione dei clienti tramite l'esperienza MTM

Per accedere al portale MTM, la tua organizzazione deve essere integrata come Elite Partner per il servizio TRM. Per diventare un contatto partner Elite askelite@microsoft.com.

## <a name="on-boarding-customers"></a>Clienti on-boarding

Per gestire i clienti tramite il portale TRM-MTM, è necessario stabilire una relazione tra il tenant dell'organizzazione partner e il cliente tramite un invito inviato dal cliente. 

## <a name="tenant-managers"></a>Responsabili tenant

Questo ruolo predefinito è configurabile solo nel portale TRM-MTM. Questo ruolo consente di assegnare un gruppo di utenti che accettano inviti, ma non sono coinvolti nella gestione delle sale per i clienti. È consigliabile configurare il ruolo. In caso contrario, solo gli utenti con il ruolo di amministratore del servizio gestito nel tenant potranno accettare gli inviti.

**Per configurare i responsabili del tenant**
 
1.  Accedere al portale TRM-MTM come amministratore globale o amministratore del servizio gestito.
2.  Passare a Tenant manager.
3.  Selezionare **Aggiungi responsabili tenant**.
4.  Nel riquadro dei dettagli cercare gli utenti o i gruppi di sicurezza.
5.  Selezionare l'utente o il gruppo.
6.  Selezionare **Aggiungi**.

### <a name="invitation-from-the-customer"></a>Invito del cliente

Il partner deve fornire il nome di dominio ai clienti. Solo i ruoli amministratore globale, amministratore del servizio gestito e responsabile tenant possono visualizzare e accettare l'invito quando accedono al portale TRM-MTM. 

> [!Note]
> Anche se questi ruoli possono visualizzare inviti e metadati del tenant di alto livello, i dati del cliente non saranno visualizzati finché non si viene assegnati un ruolo al cliente.

I dettagli sull'invito del cliente sono descritti in [Gestione multi-tenant per i clienti](multi-tenant-management-customer.md).

**Per accettare un invito in sospeso**

1. Accedere al portale TRM-MTM come amministratore globale, amministratore del servizio gestito o gestore tenant.
1. Vai a **Tenant**.
1. Selezionare l'invito con lo stato "In sospeso".
1. Rivedere i dettagli dell'invito.
1. Assegnare gli utenti che saranno gli amministratori principali di questo cliente.
1. Selezionare **Accetta** per stabilire la relazione partner-cliente.

   Se si seleziona **Nega** , l'invito viene eliminato.

   > [!Note]
   > Non esiste alcuna associazione permanente con l'utente che accetta l'invito.

   > [!Note]
   > *Se l'invito viene rifiutato accidentalmente, il cliente deve creare un nuovo invito.* 

**Per esaminare la configurazione o aggiungere altri amministratori primari per un tenant**

1. Selezionare il cliente nell'elenco **Tenant** .
1. Nel riquadro dei dettagli selezionare **Amministratori principali**.
1. Cercare l'utente o il gruppo.
1. Selezionare **Aggiungi** per confermare la selezione.

## <a name="off-boarding-customers"></a>Clienti off-boarding

Per rimuovere un cliente dall'elenco **Tenant** , è necessario rimuoverlo.

**Per rimuovere un cliente** 

1. Accedi al portale TRM-MTM come amministratore primario per il cliente che desideri rimuovere.
1. Vai a **Tenant**.
1. Seleziona il cliente che desideri rimuovere.
1. Nel riquadro dei dettagli del cliente selezionare **Rimuovi cliente**.
1. Selezionare **Elimina** nella richiesta di conferma per terminare l'associazione tra l'utente e il tenant del cliente.

## <a name="managing-partner-roles"></a>Gestione dei ruoli dei partner

I ruoli dei partner consentono di delegare le responsabilità a personale aggiuntivo. Il concetto di questi ruoli è lo stesso descritto nel [controllo dell'accesso basato sui](microsoft-teams-rooms-premium-rbac.md) ruoli, ma nel contesto di ogni cliente. Inoltre, è importante notare che i ruoli del partner sono distinti dai ruoli del cliente. I ruoli partner possono essere eliminati dal cliente. 

Il ruolo **Amministratore principale** è l'unico ruolo predefinito per ogni cliente integrato e ha quasi tutte le autorizzazioni, nel contesto del cliente, per il servizio TRM (vedere tabella 1). Le autorizzazioni del ruolo Partner** si estendono solo fino alle chat room designate dal cliente. Ad esempio, se il cliente è un'organizzazione globale e assegna al Partner la gestione di Tutte le chat room negli Stati Uniti, l'amministratore principale sarà in grado solo di gestire e delegare le autorizzazioni per tali chat room. Il Partner non ha visibilità sulle altre chat room che il Cliente può avere in altri paesi. 

**Per gestire gli utenti con il ruolo **partner** per un cliente**

1. Passare a **Impostazioni > ruoli**. 
1. Selezionare il cliente nell'elenco a discesa per cui si vuole modificare il ruolo partner.
1. Selezionare il ruolo predefinito **Amministratori principali** nell'elenco.
1. Selezionare **Attività.**
1. Nell'elenco selezionare **Amministratori assegnati.**
1. Selezionare **Membri.**
1. Selezionare **Modifica.** 
1. Cerca l'utente o il gruppo di sicurezza che vuoi aggiungere nella barra di ricerca.
1. Selezionare l'utente o il gruppo.
1. Selezionare **Salva** per confermare le modifiche.

### <a name="managing-custom-partner-roles-for-a-customer"></a>Gestione dei ruoli dei partner personalizzati per un cliente

I partner possono creare ruoli personalizzati in base alle proprie esigenze operative. Ad esempio, è possibile creare un ruolo help desk che dovrebbe avere solo autorizzazioni di gestione degli eventi imprevisti. 

**Per gestire i ruoli**

1. Passare a **Impostazioni > ruoli**. 
1. Selezionare il cliente dal menu a discesa per cui si vuole modificare il ruolo partner.
1. Creare un [ruolo personalizzato](microsoft-teams-rooms-premium-rbac.md#built-in-roles).




|Funzionalità|Autorizzazione|**Amministrazione MMR**|**Cliente potenziale del sito**|**Tech del sito**|**Amministratori principali**|
| :- | :- | :- | :- | :- | :- |
|Camere|Visualizzare| &#10004;|&#10004;|&#10004;|&#10004;|
||Modificare|&#10004;|&#10004;|&#10004;|&#10004;|
||Tasto REIMPOSTA|&#10004;||||
||Chiave di download|&#10004;|&#10004;|&#10004;||
||Annullare la registrazione|&#10004;|&#10004;|&#10004;||
||Create |&#10004;|&#10004;|||
|Gestione dei gruppi|Visualizzare|&#10004;|&#10004;||&#10004;|
||Modificare|&#10004;|&#10004;|||
||Create |&#10004;|&#10004;|||
|Gestione dell'anello di aggiornamento|Visualizzare|&#10004;|&#10004;||&#10004;|
||Modificare|&#10004;|&#10004;||&#10004;|
|Rapporti|Visualizzare|&#10004;|&#10004;||&#10004;|
||Crea evento imprevisto del cliente|&#10004;|&#10004;|&#10004;|&#10004;|
|Gestione biglietti|Visualizzare|&#10004;|&#10004;|&#10004;|&#10004;|
||Update|&#10004;|&#10004;|&#10004;|&#10004;|
|Impostazioni MMR|Visualizzare|&#10004;||||
||Modificare|&#10004;||||
|Gestione dei ruoli|Visualizzare |&#10004;|||&#10004;|
||Modificare|&#10004;|||&#10004;|

> [!Note]
> Un utente assegnato come amministratore principale per il cliente A ha autorizzazioni complete nel servizio TRM solo per quel cliente. Le autorizzazioni dell'utente nel cliente A non hanno alcuna influenza sugli altri clienti.

## <a name="security"></a>Sicurezza

I clienti finali mantengono il controllo sull'accesso ai propri dati e possono rimuovere completamente un partner o ruoli specifici in qualsiasi momento.

Con la funzionalità di accesso delegato, un partner non ottiene altri privilegi al di fuori del portale del servizio TRM. Ad esempio, usando questa funzionalità per invitare un partner a gestire sale nel servizio TRM, non vengono concesse autorizzazioni ad AAD o al Centro Amministrazione Teams o a qualsiasi altro prodotto Microsoft. Inoltre, i partner non hanno accesso alla visualizzazione o alla modifica di chat room non definite nell'ambito dell'invito.

Una volta stabilita la relazione partner-cliente, come descritto in "Clienti onboarding" di questo documento, il partner può visualizzare i dati della sala nel servizio TRM. Sono inclusi i dati presenti nel servizio TRM ma derivati da altri prodotti Microsoft. Ad esempio, i rapporti sulla qualità delle chiamate nel portale TRM derivano dai dati sulla qualità delle chiamate di Teams.

I dati si trovano nel tenant del cliente e non vengono copiati nel tenant del partner. 

Il portale MTM utilizza l'autenticazione AAD per convalidare le credenziali di accesso del partner. È importante notare che al momento i criteri di autenticazione del cliente non verranno applicati al partner. Ad esempio, se il cliente ha un criterio di autenticazione a più fattori, non si traduce nel partner.

Il cliente può estrarre i log di controllo per il servizio TRM, che include l'attività dei partner. Vedere [Registrazione di controllo nel servizio gestito di Teams Rooms](multi-tenant-auditing.md).

> [!Note]
> Il controllo di AAD e di O365 non acquisisce i log dal portale TRM.

## <a name="navigating-the-mtm-portal"></a>Esplorazione del portale MTM

Il portale MTM offre due modelli interattivi per spostarsi tra i dati dei clienti:

- Visualizzazioni aggregate in cui i dati di tutti i clienti vengono consolidati in un unico elenco e possono essere filtrati.

  > [!Note]
  > Questa visualizzazione è supportata solo nella pagina **Eventi imprevisti** quando l'opzione **Abilita tutti i biglietti** è attivata.
  >
  > ![Figura 1](../media/multi-tenant-management-partner-001.png)

 - Passaggio tenant in cui vengono visualizzati solo i dati del **cliente** selezionato nell'elenco a discesa.
