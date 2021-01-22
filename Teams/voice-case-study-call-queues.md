---
title: Case study su Teams per Contoso
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
description: Case study vocale di Teams per multi-national corporation
appliesto:
- Microsoft Teams
ms.openlocfilehash: a6ee08fa7bdeb1ded6bda384115a08048021cb67
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918732"
---
# <a name="contoso-case-study-auto-attendants-and-call-queues"></a>Case study contoso: Operatori automatici e code di chiamata

Contoso aveva familiarità con gli operatori automatici e le code di chiamata dalla distribuzione skype for Business locale. Per comprendere come impostare gli operatori automatici cloud e le code di chiamata, hanno esaminato il piano per gli operatori automatici di Teams e [le code di chiamata.](plan-auto-attendant-call-queue.md)

## <a name="requirements-depending-on-site-type"></a>Requisiti a seconda del tipo di sito

A seconda del tipo di sito, Contoso ha le esigenze seguenti:

- Tipo di sito A: sistemi di telefonia legacy tradizionali 

  Tipo di sito A necessario per mantenere lo stesso numero di telefono associato all'addetto alla reception come numero per gli operatori automatici. I reparti principali di ciascuno di questi siti hanno code di chiamata proprio da instradare ai membri del team. Esisteva una combinazione di siti che usava Sistema telefonico con Instradamento diretto e Sistema telefonico con Piani per chiamate.  

- Tipo di sito B: VoIP aziendale 

  Il tipo di sito B aveva già operatori automatici e code di chiamata che dovevano eseguire la migrazione a Teams. Contoso deve mantenere i numeri di telefono associati agli operatori automatici. Contoso ha spostato la maggior parte di questi siti nel Sistema telefonico con Piani per chiamate. Tuttavia, nelle poche località in cui i Piani per chiamate non erano disponibili, Contoso ha spostato questi siti in una configurazione di routing diretto.  

- Tipo di sito C: Skype for Business VoIP aziendale & sistema di telefonia legacy tradizionale 

  Nel tipo di sito C erano presenti operatori automatici presenti nel sistema di telefonia legacy tradizionale. Le decisioni e le configurazioni per il sito sono uguali al tipo di sito A.   

- Per tutti i tipi di sito, Contoso ha posto le domande seguenti:

  - D: Verranno utilizzati numeri nuovi o esistenti? 
    A: Contoso ha deciso di utilizzare numeri di telefono esistenti da assegnare all'account di servizio per l'operatore automatico. 

  - D: Quando sarà disponibile l'operatore automatico ad accettare le chiamate in arrivo? 
    A: Contoso ha deciso di impostare l'orario di ufficio e fare in modo che le chiamate ricevute dopo l'orario di ufficio vengono reindirizzate a un operatore automatico "non in orario di ufficio".  

  - D: In che modo le chiamate verranno instradati ai membri in una coda di chiamata: instradamento con operatore, seriale o round robin? 
    A: Contoso ha deciso di usare il routing di Attendant, 

  - D: Come si determina quando un utente dovrebbe o non dovrebbe ricevere una chiamata? 
    A: Contoso ha deciso di usare le opzioni di gestione delle chiamate per determinare se l'agente è disponibile: routing basato sulla presenza. 


## <a name="configuration"></a>Configurazione

La procedura per impostare un operatore automatico e una coda di chiamata è illustrata nella [sezione Gestire gli account delle risorse:](manage-resource-accounts.md) 

1. Ottenere un numero di servizio. 

2. Ottenere una licenza Sistema telefonico gratuita - Utente virtuale o Sistema telefonico a pagamento da usare con l'account delle risorse o una licenza Sistema telefonico.

3. Creare l'account della risorsa. È necessario un operatore automatico o una coda di chiamata per avere un account delle risorse associato. 

4. Assegnare la licenza Sistema telefonico o Sistema telefonico - Utente virtuale all'account delle risorse. Per ulteriori informazioni, consulta [Sistema telefonico Microsoft 365 - Licenza Utente virtuale.](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/virtual-user)

5. Assegnare un numero di telefono di servizio all'account delle risorse a cui sono state assegnate licenze. 

6. Creare una coda di chiamata o un operatore automatico del sistema telefonico 

7. Collega l'account della risorsa a una coda di chiamata o a un operatore automatico. 


### <a name="sites-with-phone-system-with-direct-routing"></a>Siti con Sistema telefonico con instradamento diretto 

Contoso ha dovuto impostare il numero di telefono fornito dal gestore locale come numero di servizio in Office 365. 

- Per impostare un numero di telefono disponibile tramite instradamento diretto, Contoso ha seguito le istruzioni disponibili in [Gestisci account risorse.](manage-resource-accounts.md) Poiché Office 365 non è a conoscenza dei numeri di telefono locali, Contoso ha usato PowerShell per completare la configurazione.   

- Per configurare l'operatore automatico Cloud, Contoso ha seguito i passaggi descritti in [Configurare un operatore](create-a-phone-system-auto-attendant.md)automatico Cloud. 

- Per impostare una coda di chiamata Cloud, Contoso ha seguito i passaggi descritti in [Creare una coda di chiamata Cloud.](create-a-phone-system-call-queue.md)  


### <a name="sites-with-phone-system-with-calling-plan"></a>Siti con Sistema telefonico con piano per chiamate

Contoso ha dovuto eseguire il portabilità del numero di telefono usato per gli operatori automatici VoIP aziendale Skype for Business al Sistema telefonico Office 365. Ciò consentiva di assegnare lo stesso numero come numero di servizio per l'uso come operatore automatico. 

- Per trasferire il numero di telefono, Contoso ha seguito le istruzioni in Trasferisci numeri di telefono in [Teams](https://docs.microsoft.com/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams) e ha ottenuto altre indicazioni su Gestione dei numeri di telefono [per l'organizzazione.](https://docs.microsoft.com/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)

- Per configurare un operatore automatico Cloud, Contoso ha seguito i passaggi descritti in [Configurare un operatore](create-a-phone-system-auto-attendant.md)automatico Cloud.

-  Per impostare una coda di chiamata Cloud, Contoso ha seguito i passaggi descritti in [Creare una coda di chiamata Cloud.](create-a-phone-system-call-queue.md)  

 