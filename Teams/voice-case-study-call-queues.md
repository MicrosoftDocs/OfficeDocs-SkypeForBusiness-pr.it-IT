---
title: Case Study di teams Voice contoso
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: Case Study di teams Voice per società multinazionali
appliesto:
- Microsoft Teams
ms.openlocfilehash: 780d812b4e6e56b28b867ace14dbf1d5f6170302
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786023"
---
# <a name="contoso-case-study-auto-attendants-and-call-queues"></a>Case Study di Contoso: operatori automatici e code di chiamata

Contoso ha familiarità con gli operatori automatici e le code di chiamata dalla distribuzione di Skype for business locale. Per informazioni su come configurare gli operatori automatici del cloud, hanno esaminato gli [operatori automatici del cloud](what-are-phone-system-auto-attendants.md) e l' [esempio Small Business-configurare l'esercitazione](tutorial-org-aa.yml)per l'operatore automatico. Per informazioni sulle opzioni disponibili per la configurazione delle code di chiamata, contoso Recensito [Crea una coda di chiamata cloud](create-a-phone-system-call-queue.md).  

## <a name="requirements-depending-on-site-type"></a>Requisiti a seconda del tipo di sito

A seconda del tipo di sito, Contoso ha le seguenti esigenze:

- Tipo di sito A: sistemi di telefonia legacy tradizionali 

  Tipo di sito A necessario per conservare lo stesso numero di telefono associato al receptionist come numero per gli operatori automatici. I reparti chiave per ognuno di questi siti avrebbero le proprie code di chiamata che instradano i membri del team. C'era una combinazione di siti che usavano sistema telefonico con routing diretto e sistema telefonico con piani di chiamata.  

- Tipo di sito B: Skype for Business Enterprise Voice 

  Il tipo di sito B aveva gli operatori automatici esistenti e le code di chiamata necessarie per eseguire la migrazione a teams. Contoso necessario per conservare i numeri di telefono associati agli operatori automatici. Contoso ha spostato la maggior parte di questi siti nel sistema telefonico con piani di chiamata. Tuttavia, nelle poche posizioni in cui i piani per le chiamate non erano disponibili, Contoso ha spostato questi siti in una configurazione di routing diretta.  

- Tipo di sito C: Skype for Business Enterprise Voice & sistema tradizionale di telefonia legacy 

  Il tipo di sito C aveva gli operatori automatici esistenti che risiedevano nel sistema tradizionale di telefonia legacy. Le decisioni e le configurazioni per questo sito erano le stesse del tipo di sito A.   

- Per tutti i tipi di sito, Contoso ha richiesto le seguenti domande:

  - D: useremo numeri nuovi o esistenti? 
    A: Contoso ha deciso di usare i numeri di telefono esistenti da assegnare all'account del servizio per l'operatore automatico. 

  - D: quando l'operatore automatico sarà disponibile ad accettare le chiamate in arrivo? 
    A: Contoso ha deciso di impostare l'orario di ufficio e di ricevere chiamate ricevute dopo l'orario di ufficio reindirizzato a un operatore automatico "after-hours".  

  - D: in che modo le chiamate verranno instradate ai membri in una coda di chiamata: il routing di Attendant, seriale o Round Robin? 
    A: Contoso ha deciso di usare il routing di Attendant 

  - D: come si determina quando un utente deve o non deve ricevere una chiamata? 
    A: Contoso ha deciso di usare le opzioni di gestione delle chiamate per determinare se l'agente è disponibile: routing basato sulla presenza. 


## <a name="configuration"></a>Configurazione

I passaggi per configurare un operatore automatico e una coda di chiamata includono gli elementi seguenti descritti in [gestire gli account delle risorse](manage-resource-accounts.md): 

1. Ottenere un numero di servizio. 

2. Ottenere un sistema telefonico gratuito-licenza per gli utenti virtuali o una licenza per il sistema telefonico a pagamento da usare con l'account delle risorse o con una licenza per il sistema telefonico.

3. Creare l'account delle risorse. Per avere un account di risorse associato è necessario un operatore automatico o una coda di chiamata. 

4. Assegnare il sistema telefonico o un sistema telefonico-licenza utente virtuale per l'account delle risorse. Per altre informazioni, vedere [sistema telefonico Microsoft 365-licenza per gli utenti virtuali](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/virtual-user).

5. Assegnare un numero di telefono del servizio all'account della risorsa a cui sono state assegnate le licenze. 

6. Creare una coda di chiamata di sistema telefonico o un operatore automatico 

7. Collegare l'account delle risorse con una coda di chiamata o un operatore automatico. 


### <a name="sites-with-phone-system-with-direct-routing"></a>Siti con sistema telefonico con routing diretto 

Contoso ha dovuto configurare il numero di telefono fornito dal vettore locale come numero di servizio in Office 365. 

- Per configurare un numero di telefono disponibile tramite routing diretto, Contoso ha seguito le istruzioni disponibili in [Gestisci account risorse](manage-resource-accounts.md). Poiché Office 365 non è a conoscenza dei numeri di telefono locali, Contoso ha usato PowerShell per completare la configurazione.   

- Per configurare l'operatore automatico cloud, Contoso ha seguito i passaggi descritti in [configurare un operatore automatico cloud](create-a-phone-system-auto-attendant.md). 

- Per configurare una coda di chiamata cloud, Contoso ha seguito i passaggi illustrati in [creare una coda di chiamata cloud](create-a-phone-system-call-queue.md).  


### <a name="sites-with-phone-system-with-calling-plan"></a>Siti con sistema telefonico con un piano per le chiamate

Contoso ha dovuto trasferire il numero di telefono usato per gli operatori automatici di Skype for Business VoIP per Office 365 Phone System. Ciò ha consentito di assegnare lo stesso numero come numero di servizio da usare come operatore automatico. 

- Per trasferire il numero di telefono, Contoso ha seguito le istruzioni in [trasferimento di numeri di telefono a teams](https://docs.microsoft.com/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams) e ha ottenuto ulteriori indicazioni [per gestire i numeri di telefono per l'organizzazione](https://docs.microsoft.com/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization).

- Per configurare un operatore automatico cloud, Contoso ha seguito i passaggi descritti in [configurare un operatore automatico cloud](create-a-phone-system-auto-attendant.md).

-  Per configurare una coda di chiamata cloud, Contoso ha seguito i passaggi illustrati in [creare una coda di chiamata cloud](create-a-phone-system-call-queue.md).  

 