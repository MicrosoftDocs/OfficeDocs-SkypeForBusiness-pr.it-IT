---
title: Sistema telefonico Microsoft 365 - Licenze utente virtuale
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: waseemh
ms.topic: reference
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom:
- Licensing
- LIL_Placement
- seo-marvel-apr2020
description: Informazioni su come assegnare una licenza gratuita sistema telefonico-utente virtuale o una licenza utente sistema telefonico a pagamento agli account delle risorse dell'organizzazione.
ms.openlocfilehash: 8e5322ccf7e3e7ad05c499b3dbcfdac65d0dfedb
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116924"
---
# <a name="microsoft-365-phone-system--virtual-user-license"></a>Sistema telefonico Microsoft 365 - Licenza utente virtuale

Le organizzazioni con licenza Sistema telefonico gli utenti possono assegnare agli account delle risorse una licenza gratuita Sistema telefonico Microsoft 365 - Utente virtuale o una licenza utente sistema telefonico a pagamento. Non è necessario un piano per chiamate. Tutti gli operatori automatici o le code di chiamata richiedono un account di risorsa associato. Per poter applicare un numero di telefono all'account della risorsa, gli account delle risorse che richiedono un numero di telefono devono avere una licenza gratuita per Microsoft 365 Phone System – Virtual User o una licenza utente sistema telefonico a pagamento.

> [!TIP]
> Non è necessaria alcuna licenza per gli account delle risorse che verranno usati con operatori automatici annidati o code di chiamata a cui non è assegnato un numero di telefono. Per informazioni di riferimento, vedere il diagramma seguente: 

![Licenze per utenti virtuali](../media/resource-account.png)

## <a name="virtual-user-license-allocation"></a>Assegnazione licenze utente virtuale

All'organizzazione è assegnato Microsoft 365 Phone System - Licenze per utenti virtuali a seconda delle dimensioni complessive. Qualsiasi organizzazione che abbia almeno una licenza, tra cui Sistema telefonico o con Sistema telefonico aggiunto, ha 25 licenze per utenti virtuali disponibili senza costi aggiuntivi. Quando si aggiungono 10 licenze utente di Sistema telefonico nell'organizzazione, diventa disponibile un altro sistema telefonico Microsoft 365 : la licenza per l'utente virtuale diventa disponibile.

> [!NOTE]
> Sistema telefonico è una licenza per componenti aggiuntivi disponibile con Microsoft 365 e Office 365 E1 ed E3. Sistema telefonico è incluso anche nell'ambito delle licenze Microsoft 365 E5, Office 365 E5 e Microsoft 365 Business Voice.

Se l'organizzazione usa il sistema telefonico Microsoft 365 gratuito - Licenze utente virtuale per la creazione di nodi di operatore automatico o coda di chiamata, è comunque possibile usare le licenze del sistema telefonico a pagamento con un account delle risorse. La maggior parte delle organizzazioni avrà un numero di licenze utente virtuale sufficiente in base al piano di scalabilità. 

### <a name="license-allocation-example"></a>Esempio di assegnazione delle licenze

Contoso, Inc. ha acquistato 600 licenze che includevano Sistema telefonico (una per ogni dipendente). A Contoso sono assegnate 25 licenze iniziali più 60 sistema telefonico Microsoft 365 - Licenze utente virtuale, 85 in totale. L'organizzazione ha 90 code di chiamata e operatori automatici con numeri di telefono. Devono assegnare tutte le licenze di Sistema telefonico Microsoft 365 - Utente virtuale e ottenere cinque licenze di sistema telefonico a prezzo normale.

Contoso dovrebbe prendere in considerazione la riprogettazione dell'operatore automatico e del sistema di coda di chiamata. Se usano meno numeri di telefono e più nodi annidati che non hanno bisogno di un numero di telefono, semplificano l'implementazione e riducono i costi.

## <a name="how-to-buy-microsoft-365-phone-system--virtual-user-licenses"></a>Come acquistare Microsoft 365 Phone System - Licenze utente virtuale

1. Accedere all'interfaccia di amministrazione di Microsoft 365.
2. Passare a **Componenti** aggiuntivi Servizi di acquisto  >    >  **fatturazione**
3. Scorrere fino alla fine per trovare la **licenza Microsoft 365 Phone System - Virtual User.** Seleziona **Acquista ora**.

> [!NOTE]
> Tenere presente che è comunque necessario  **acquistare** la licenza anche se ha un costo pari a zero.

## <a name="change-an-existing-resource-account-to-use-a-microsoft-365-phone-system--virtual-user-license"></a>Modificare un account delle risorse esistente per usare una licenza Di sistema telefonico - Utente virtuale di Microsoft 365

Se si decide di cambiare la licenza dell'account della risorsa da una licenza sistema telefonico a una licenza Sistema telefonico Microsoft 365 - Utente virtuale:

1. Ottenere la nuova licenza Sistema telefonico Microsoft 365 - Utente virtuale.
2. Seguire i passaggi collegati nell'interfaccia di amministrazione di Microsoft 365 per [spostare gli utenti in un abbonamento diverso.](/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription)

> [!WARNING]
> Rimuovere sempre una licenza di sistema telefonico completa e assegnare la licenza Microsoft 365 Phone System - Virtual User nella stessa attività di licenza. Se si rimuove la vecchia licenza, si salvano le modifiche all'account, si aggiunge la nuova licenza e quindi si salvano di nuovo le impostazioni dell'account, l'account della risorsa potrebbe non funzionare più come previsto. In questo caso, è consigliabile creare un nuovo account delle risorse per la licenza Sistema telefonico - Utente virtuale di Microsoft 365 e rimuovere l'account delle risorse danneggiato. 

## <a name="related-information"></a>Informazioni correlate

[Operatore automatico e servizio Code di chiamata](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521)

[Gestire gli account di risorsa in Microsoft Teams](../manage-resource-accounts.md)