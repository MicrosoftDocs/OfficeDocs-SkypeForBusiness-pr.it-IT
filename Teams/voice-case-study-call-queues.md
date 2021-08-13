---
title: 'Teams caso di studio contoso vocale: operatori automatici e code di chiamata'
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
description: 'Teams case study vocale per multinazionali: operatori automatici e code di chiamata'
appliesto:
- Microsoft Teams
ms.openlocfilehash: bf1d7a5457af0d7463207c0bdbc9d50433b3142e2f72e7efc7f8c89ade82bc93
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54296423"
---
# <a name="contoso-case-study-auto-attendants-and-call-queues"></a>Case study contoso: Operatori automatici e code di chiamata

Contoso aveva familiarità con gli operatori automatici e le code di chiamata dalla distribuzione Skype for Business locale. Per informazioni su come configurare gli operatori automatici cloud e le code di chiamata, hanno esaminato Pianificare gli operatori automatici Teams e [le code di chiamata.](plan-auto-attendant-call-queue.md)

## <a name="requirements-depending-on-site-type"></a>Requisiti a seconda del tipo di sito

A seconda del tipo di sito, Contoso ha le esigenze seguenti:

- Tipo di sito A: sistemi di telefonia legacy tradizionali 

  Tipo di sito A necessario per mantenere lo stesso numero di telefono associato all'addetto alla ricezione del numero per gli operatori automatici. I reparti chiave di ognuno di questi siti avrebbero code di chiamata che verrebbero indirizzate ai membri del team. C'era una combinazione di siti che usava Sistema telefonico routing diretto e Sistema telefonico con i piani per chiamate.  

- Tipo di sito B: Skype for Business VoIP aziendale 

  Il tipo di sito B aveva operatori automatici e code di chiamata esistenti che dovevano eseguire la migrazione a Teams. Contoso doveva mantenere i numeri di telefono associati agli operatori automatici. Contoso ha spostato la maggior parte di questi siti Sistema telefonico piani per chiamate. Tuttavia, nelle poche posizioni in cui i piani per chiamate non erano disponibili, Contoso ha spostato questi siti in una configurazione Di routing diretto.  

- Tipo di sito C: Skype for Business VoIP aziendale & tradizionale sistema di telefonia legacy 

  Il tipo di sito C aveva operatori automatici esistenti che risiedevano nel sistema di telefonia legacy tradizionale. Le decisioni e le configurazioni per questo sito sono state le stesse del tipo di sito A.   

- Per tutti i tipi di sito, Contoso ha posto le domande seguenti:

  - D: Verranno utilizzati numeri nuovi o esistenti? 
    A: Contoso ha deciso di usare i numeri di telefono esistenti da assegnare all'account del servizio per l'operatore automatico. 

  - D: Quando sarà disponibile l'operatore automatico per accettare le chiamate in arrivo? 
    A: Contoso ha deciso di impostare l'orario di ufficio e di ricevere chiamate dopo l'orario di ufficio reindirizzate a un operatore automatico "dopo l'orario di ufficio".  

  - D: Come verranno instradati le chiamate ai membri di una coda di chiamata: instradamento operatore, seriale o round robin? 
    A: Contoso ha deciso di usare il routing dell'operatore, 

  - D: Come verrà determinato quando un utente deve o meno ricevere una chiamata? 
    A: Contoso ha deciso di usare le opzioni di gestione delle chiamate per determinare se l'agente è disponibile: routing basato sulla presenza. 


## <a name="configuration"></a>Configurazione

I passaggi per configurare un operatore automatico e una coda di chiamata sono i seguenti descritti in [Gestire gli account delle risorse:](manage-resource-accounts.md) 

1. Ottenere un numero di servizio. 

2. Ottenere una licenza Sistema telefonico - Utente virtuale o una licenza Sistema telefonico a pagamento da usare con l'account della risorsa o una Sistema telefonico licenza.

3. Creare l'account della risorsa. Un operatore automatico o una coda di chiamata deve avere un account di risorsa associato. 

4. Assegnare la Sistema telefonico o una Sistema telefonico - Licenza utente virtuale all'account della risorsa. Per altre informazioni, vedere Microsoft 365 Sistema telefonico [- Licenza utente virtuale](./teams-add-on-licensing/virtual-user.md).

5. Assegnare un numero di telefono del servizio all'account della risorsa a cui sono state assegnate le licenze. 

6. Creare una coda Sistema telefonico chiamata o un operatore automatico 

7. Collegare l'account della risorsa a una coda di chiamata o a un operatore automatico. 


### <a name="sites-with-phone-system-with-direct-routing"></a>Siti con Sistema telefonico con routing diretto 

Contoso ha dovuto configurare il numero di telefono fornito dal gestore locale come numero di servizio in Office 365. 

- Per configurare un numero di telefono disponibile tramite Routing diretto, Contoso ha seguito le istruzioni disponibili in [Gestire gli account delle risorse.](manage-resource-accounts.md) Poiché Office 365 non è a conoscenza dei numeri di telefono locali, Contoso ha usato PowerShell per completare la configurazione.   

- Per configurare l'operatore automatico cloud, Contoso ha seguito i passaggi descritti in [Configurare un operatore automatico cloud.](create-a-phone-system-auto-attendant.md) 

- Per configurare una coda di chiamate cloud, Contoso ha seguito i passaggi descritti in [Creare una coda di chiamata cloud.](create-a-phone-system-call-queue.md)  


### <a name="sites-with-phone-system-with-calling-plan"></a>Siti con Sistema telefonico piano chiamate

Contoso ha dovuto convertire il numero di telefono usato per Skype for Business VoIP aziendale operatori automatici in Sistema telefonico di Office 365. In questo modo è possibile assegnare lo stesso numero come numero di servizio da usare come operatore automatico. 

- Per trasferire il numero di telefono, Contoso ha seguito le istruzioni [in](./phone-number-calling-plans/transfer-phone-numbers-to-teams.md) Trasferire i numeri di telefono in Teams e ha ottenuto altre indicazioni in Gestire i numeri di telefono [per l'organizzazione.](./manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

- Per configurare un operatore automatico cloud, Contoso ha seguito i passaggi descritti in [Configurare un operatore automatico cloud.](create-a-phone-system-auto-attendant.md)

-  Per configurare una coda di chiamate cloud, Contoso ha seguito i passaggi descritti in [Creare una coda di chiamata cloud.](create-a-phone-system-call-queue.md)  

