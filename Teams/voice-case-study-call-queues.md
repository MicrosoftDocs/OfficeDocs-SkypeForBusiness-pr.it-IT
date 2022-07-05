---
title: 'Caso di studio teams voice Contoso: operatori automatici e code di chiamata'
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
description: 'Case study su Teams voice per società multinazionali: operatori automatici e code di chiamata'
appliesto:
- Microsoft Teams
ms.openlocfilehash: 50d1ee2d384b200aeab6eefd6ca2de623015b6f2
ms.sourcegitcommit: a6f4c459b9c8154814a8a5b098bde1e374348c99
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/05/2022
ms.locfileid: "66615842"
---
# <a name="contoso-case-study-auto-attendants-and-call-queues"></a>Case study di Contoso: Operatori automatici e code di chiamata

Contoso aveva familiarità con gli operatori automatici e le code di chiamata dalla distribuzione locale Skype for Business. Per capire come configurare gli operatori automatici cloud e le code di chiamata, hanno esaminato [il piano per gli operatori automatici e le code di chiamata di Teams](plan-auto-attendant-call-queue.md).

## <a name="requirements-depending-on-site-type"></a>Requisiti a seconda del tipo di sito

A seconda del tipo di sito, Contoso aveva le seguenti esigenze:

- Sito tipo A: sistemi di telefonia legacy tradizionali 

  Sito Tipo A necessario per mantenere lo stesso numero di telefono associato all'addetto alla reception del numero per gli operatori automatici. I reparti principali di ognuno di questi siti hanno le proprie code di chiamata che verrebbero instradate ai membri del team. C'era una combinazione di siti che usavano Sistema telefonico con Routing diretto e Sistema telefonico con Piani per chiamate.  

- Tipo di sito B: Skype for Business VoIP aziendale 

  Il sito di tipo B disponeva di operatori automatici e code di chiamata esistenti, necessari per eseguire la migrazione a Teams. Contoso deve mantenere i numeri di telefono associati agli operatori automatici. Contoso ha spostato la maggior parte di questi siti in Sistema telefonico con Piani per chiamate. Tuttavia, nelle poche posizioni in cui i Piani per chiamate non erano disponibili, Contoso ha spostato questi siti in una configurazione routing diretto.  

- Tipo di sito C: Skype for Business VoIP aziendale & sistema di telefonia legacy tradizionale 

  Il sito tipo C aveva operatori automatici esistenti che risiedevano nel sistema di telefonia legacy tradizionale. Le decisioni e le configurazioni per questo sito sono le stesse del tipo A.   

- Per tutti i tipi di sito, Contoso ha posto le domande seguenti:

  - D: Useremo numeri nuovi o esistenti? 
    R: Contoso ha deciso di usare i numeri di telefono esistenti per essere assegnati all'account del servizio per l'operatore automatico. 

  - D: Quando l'operatore automatico sarà disponibile per accettare le chiamate in arrivo? 
    R: Contoso ha deciso di impostare l'orario di ufficio e di reindirizzare le chiamate al di fuori dell'orario di ufficio a un operatore automatico "fuori orario".  

  - D: Come verranno instradate le chiamate ai membri in una coda di chiamata: routing operatore, seriale o round robin? 
    R: Contoso ha deciso di usare il routing Attendant, 

  - D: Come determineremo quando un utente deve o non deve ricevere una chiamata? 
    R: Contoso ha deciso di usare le opzioni di gestione delle chiamate per determinare se l'agente è disponibile: routing basato sulla presenza. 

## <a name="configuration"></a>Configurazione

I passaggi per configurare un operatore automatico e una coda di chiamata includono quanto segue, descritto in [Gestire gli account delle risorse](manage-resource-accounts.md):

1. Ottenere un numero di servizio.

2. Ottenere una licenza gratuita **per l'account di risorsa Telefono di Microsoft Teams** o una licenza a pagamento sistema telefonico da usare con l'account della risorsa o una licenza Sistema telefonico.

3. Creare l'account della risorsa. Per avere un account di risorsa associato, è necessario un operatore automatico o una coda di chiamata.

4. Assegnare **una licenza** **Teams Phone Standard o Telefono di Microsoft Teams account risorsa** all'account della risorsa. Per altre informazioni, vedere [Telefono di Microsoft Teams licenza Account risorse](./teams-add-on-licensing/virtual-user.md).

5. Assegnare un numero di telefono di servizio all'account della risorsa a cui sono assegnate licenze.

6. Crea una coda di chiamata o un operatore automatico sistema telefonico.

7. Collega l'account della risorsa a una coda di chiamata o a un operatore automatico.

### <a name="sites-with-phone-system-with-direct-routing"></a>Siti con sistema telefonico con routing diretto

Contoso doveva configurare il numero di telefono fornito dal gestore locale come numero di servizio in Office 365.

- Per configurare un numero di telefono disponibile tramite Direct Routing, Contoso ha seguito le istruzioni disponibili in [Manage Resource Accounts](manage-resource-accounts.md). Poiché Office 365 non è a conoscenza dei numeri di telefono locali, Contoso ha usato PowerShell per completare la configurazione.   

- Per configurare l'operatore automatico cloud, Contoso ha seguito i passaggi descritti in [Configurare un operatore automatico cloud](create-a-phone-system-auto-attendant.md). 

- Per configurare una coda di chiamata cloud, Contoso ha seguito i passaggi descritti in [Creare una coda di chiamata cloud](create-a-phone-system-call-queue.md).  


### <a name="sites-with-phone-system-with-calling-plan"></a>Siti con sistema telefonico con piano per chiamate

Contoso doveva trasferire in Sistema telefonico di Office 365 il numero di telefono usato per Skype for Business VoIP aziendale gli operatori automatici. Ciò ha consentito l'assegnazione dello stesso numero come numero di servizio per l'uso come operatore automatico. 

- Per trasferire il numero di telefono, Contoso ha seguito le istruzioni in [Trasferire i numeri di telefono in Teams](./phone-number-calling-plans/transfer-phone-numbers-to-teams.md) e ha ottenuto indicazioni aggiuntive in [Gestire i numeri di telefono per l'organizzazione](./manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

- Per configurare un operatore automatico cloud, Contoso ha seguito i passaggi descritti in [Configurare un operatore automatico cloud](create-a-phone-system-auto-attendant.md).

-  Per configurare una coda di chiamata cloud, Contoso ha seguito i passaggi descritti in [Creare una coda di chiamata cloud](create-a-phone-system-call-queue.md).  

