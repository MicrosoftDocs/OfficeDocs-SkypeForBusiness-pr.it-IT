---
title: Gestione dei clienti multi-tenant per i partner
author: donnah007
ms.author: v-donnahill
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
description: Gestione dei clienti Mult-tenant per i partner.
f1keywords: ''
ms.openlocfilehash: edafdf182e0d27ec5c5524e9411b80de866d7f02
ms.sourcegitcommit: c8951fe3504c1776d7aec14b79605aaf5d317e7f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/08/2021
ms.locfileid: "61331240"
---
# <a name="multi-tenant-customer-management-for-partners"></a>Gestione dei clienti multi-tenant per i partner

La gestione multi-tenant (MTM) nel servizio Teams Rooms Managed (TRM) consente alle organizzazioni partner di gestire più clienti in un'unica posizione, con le proprie credenziali di dominio. Gli utenti partner potranno vedere solo le chat room dei clienti a cui sono assegnate per la gestione. È possibile applicare ruoli personalizzati per ogni cliente nel tenant MTM, offrendo alle organizzazioni partner un controllo granulare delle autorizzazioni per le risorse del cliente. 

È possibile accedere al portale MTM tramite questo [collegamento.](https://partner.rooms.microsoft.com/)

> [!Note] 
> Le organizzazioni partner non possono gestire le proprie chat room tramite il portale MTM. Queste chat room possono essere gestite nel [portale TRM.](https://portal.rooms.microsoft.com/) 

## <a name="pre-requisites-for-managing-your-customers-through-the-mtm-experience"></a>Prerequisiti per la gestione dei clienti tramite l'esperienza MTM

Per accedere al portale MTM, l'organizzazione deve essere onboarded come partner Elite per il servizio TRM. Per diventare un contatto partner Elite askelite@microsoft.com.


## <a name="on-boarding-customers"></a>Clienti a bordo

Per gestire i clienti tramite il portale TRM-MTM, è necessario stabilire una relazione tra il tenant dell'organizzazione partner e il cliente tramite un invito inviato dal cliente. 

### <a name="invitation-from-the-customer"></a>Invito del cliente

Il partner fornisce i nomi dei principi utente (UPN) degli utenti che saranno amministratori primari assegnati al cliente. Solo gli utenti identificati nell'invito possono vedere e accettare l'invito quando a loro volta a questo portale. 

> [!Note]
> Anche se si hanno privilegi elevati, ad esempio l'amministratore globale, l'invito non verrà visualizzato a meno che non si venga aggiunti esplicitamente. 

I dettagli sull'invito al cliente sono descritti in [Gestione multi-tenant per i clienti](multi-tenant-management-customer.md).

**Per accettare un invito in sospeso**

1. Accedere al portale TRM-MTM come uno degli utenti dell'invito.
1. Passare a **Clienti**.
1. Selezionare l'invito visualizzato con lo stato "In sospeso".
1. Esaminare i dettagli dell'invito.
1. Selezionare **Accetta** per stabilire la relazione partner-cliente.

   Se **si seleziona Nega,** l'invito per l'utente che lo nega. L'invito è ancora disponibile per altri utenti che non hanno ancora agito.

   > [!Note]
   > L'invito è univoco e indipendente per ogni utente. Il primo utente che accetta stabilisce il collegamento tra il partner e il tenant del cliente. Non esiste alcuna associazione permanente con l'utente che stabilisce il collegamento. Gli utenti successivi che accettano l'invito vengono aggiunti come amministratori principali.

   > [!Note]
   > *Se un utente partner nega accidentalmente l'invito, è meglio che un altro utente lo asezioni semplicemente al ruolo Partner (o a qualsiasi altro ruolo RBAC) per quel cliente.* 

Dopo aver accettato l'invito, l'utente viene aggiunto automaticamente come amministratore principale per il tenant del cliente. 

Per rivedere la configurazione per questo tenant, selezionare il cliente **nell'elenco** Clienti.


## <a name="off-boarding-customers"></a>Clienti fuori bordo

Per rimuovere un cliente dall'elenco Clienti, è necessario rimuoverlo.

**Per rimuovere un cliente** 

1. Accedere al portale TRM-MTM come amministratore principale del cliente da rimuovere.
1. Passare a **Clienti**.
1. Selezionare il cliente da rimuovere.
1. Nel riquadro dei dettagli del cliente selezionare **Rimuovi cliente**.
1. Selezionare **Elimina** nella richiesta di conferma per terminare l'associazione tra l'utente e il tenant del cliente.


## <a name="managing-partner-roles"></a>Gestione dei ruoli dei partner

I ruoli dei partner consentono di delegare le responsabilità a personale aggiuntivo. Il concetto di questi ruoli è lo stesso descritto [in](microsoft-teams-rooms-premium-rbac.md)Controllo dell'accesso basato sui ruoli, ma nel contesto di ogni cliente. Inoltre, è importante notare che i ruoli dei partner sono distinti dai ruoli del cliente. I ruoli partner possono essere eliminati dal cliente. 

Il **ruolo Amministratori** principali è l'unico ruolo predefinito per ogni cliente integrato e ha quasi tutte le autorizzazioni , nel contesto del cliente, per il servizio TRM (vedere la tabella 1). Le autorizzazioni per il ruolo partner** si estendono solo fino alle chat room designate dal cliente. Ad esempio, se cCustomer è un'organizzazione globale e assegna al partner la gestione di tutte le chat room degli Stati Uniti, l'amministratore principale potrà gestire e delegare le autorizzazioni solo per tali chat room. Il Partner non ha visibilità per altre sale che il Cliente potrebbe avere in altri paesi. 

> [!Important]
> Deve essere sempre presente almeno un utente nel **ruolo di amministratore** principale.

**Per gestire gli utenti nel **ruolo partner** per un cliente**

1. Passare a **Impostazioni > ruoli**. 
1. Selezionare il cliente nell'elenco a discesa di cui si vuole modificare il ruolo di partner.
1. Selezionare il **ruolo predefinito** Amministratori principali nell'elenco.
1. Selezionare **Attività.**
1. Nell'elenco selezionare **Amministratori invitati.**
1. Selezionare **Membri.**
1. Fare clic su **Seleziona modifica.** 
1. Cercare l'utente o il gruppo di sicurezza da aggiungere nella barra di ricerca.
1. Selezionare l'utente o il gruppo.
1. Fare clic su **Seleziona** salva per confermare le modifiche.

### <a name="managing-custom-partner-roles-for-a-customer"></a>Gestione dei ruoli dei partner personalizzati per un cliente

I partner possono creare ruoli personalizzati in base ai requisiti operativi. Ad esempio, è possibile creare un ruolo dell'help desk che deve avere solo le autorizzazioni di gestione degli eventi imprevisti. 

**Per gestire i ruoli**

1. Passare a **Impostazioni > ruoli**. 
1. Selezionare il cliente nell'elenco a discesa di cui si vuole modificare il ruolo di partner.
1. Creare un [ruolo personalizzato.](microsoft-teams-rooms-premium-rbac.md#built-in-roles)




|Funzionalità|Autorizzazione|**Amministratore MMR**|**Cliente potenziale del sito**|**Tech del sito**|**Amministratori principali**|
| :- | :- | :- | :- | :- | :- |
|Sale|Visualizzare|||||
||Modifica|||||
||Chiave di reimpostazione|||||
||Chiave di download|||||
||Annullare la registrazione|||||
|Gestione dei gruppi|Create |||||
||Visualizzare|||||
||Modifica|||||
|Aggiornare la gestione degli anelli|Create |||||
||Visualizzare|||||
||Modifica|||||
|Report|Visualizzare|||||
|Gestione dei biglietti|Creare un evento imprevisto per i clienti|||||
||Visualizzare|||||
||Update|||||
|MmR Impostazioni|Visualizzare|||||
||Modifica|||||
|Gestione ruoli|Visualizzare |||||
||Modifica|||||

> [!Note]
> Un utente assegnato come amministratore principale per il cliente A ha le autorizzazioni complete nel servizio TRM solo per quel cliente. Le autorizzazioni dell'utente nel cliente A non hanno alcuna influenza sugli altri clienti.

## <a name="security"></a>Sicurezza

I clienti finali mantengono il controllo sull'accesso ai propri dati e possono rimuovere completamente un partner o ruoli specifici in qualsiasi momento.

Con la funzionalità di accesso con delega, un partner non acquisisce altri privilegi all'esterno del portale del servizio TRM. Ad esempio, usando questa caratteristica per invitare un partner a gestire le chat room nel servizio TRM, non vengono concesse autorizzazioni a AAD o all'interfaccia di amministrazione di Teams o a qualsiasi altro prodotto Microsoft. Inoltre, i partner non hanno accesso per visualizzare o modificare le chat room non definite nell'ambito dell'invito.

Una volta stabilita la relazione partner-cliente, come descritto nella sezione "Onboarding dei clienti" di questo documento, il partner può visualizzare i dati della sala nel servizio TRM. Sono inclusi tutti i dati presenti nel servizio TRM, ma derivati da altri prodotti Microsoft. Ad esempio, i report sulla qualità delle chiamate nel portale TRM derivano Teams dati sulla qualità delle chiamate.

I dati risiedono nel tenant del cliente e non vengono copiati nel tenant del partner. 

Il portale MTM usa AAD autenticazione per convalidare le credenziali di accesso del partner. È importante tenere presente che al momento i criteri di autenticazione del cliente non verranno applicati al partner. Ad esempio, se il cliente ha un criterio di autenticazione a più fattori, non viene tradotto nel partner.

Il cliente può estrarre i log di controllo per il servizio TRM, che include l'attività dei partner. Vedere [Registrazione di controllo nel servizio Teams Rooms gestito](multi-tenant-auditing.md).

> [!Note]
> AAD controllo e il controllo di O365 non acquisiscono i log dal portale TRM.

## <a name="navigating-the-mtm-portal"></a>Esplorazione del portale MTM

Il portale MTM include due modelli interattivi per spostarsi tra i dati dei clienti:

- Le visualizzazioni aggregate sono dati di tutti i clienti consolidati in un unico elenco e possono essere filtrati.

  > [!Note]
  > Questa visualizzazione è supportata solo nella **pagina** Eventi imprevisti quando la visualizzazione Abilita tutti i **ticket** è attivata.

  ![Figura 1](../media/multi-tenant-management-partner-001.png)

 - Passaggio del tenant in cui vengono visualizzati solo i dati del **cliente** selezionato nell'elenco a discesa.
