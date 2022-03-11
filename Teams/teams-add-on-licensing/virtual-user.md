---
title: Microsoft Teams Telefono Standard - Licenze utente virtuale
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
ms.localizationpriority: medium
ms.custom:
- Licensing
- LIL_Placement
- seo-marvel-apr2020
description: Informazioni su come assegnare licenze Teams Telefono free Teams Telefono - Licenze utente virtuale o una licenza utente standard Teams Telefono a pagamento agli account delle risorse dell'organizzazione.
ms.openlocfilehash: 542d80a8cb463df01e6e232454b2454a939a457b
ms.sourcegitcommit: ff975c21725e1812e6db8fc9fe37de1362f168c3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/11/2022
ms.locfileid: "63435730"
---
# <a name="microsoft-teams-phone-standard--virtual-user-licenses"></a>Microsoft Teams Telefono Standard - Licenze utente virtuale

Le organizzazioni con Teams Telefono Standard o Teams Telefono con piano chiamate gli utenti con licenza possono assegnare una licenza *gratuita Microsoft Teams Telefono Standard – Utente* virtuale o una licenza Teams Telefono *Standard a pagamento*  licenza utente per gli account delle risorse. Un piano per le chiamate Microsoft non è sempre necessario ([vedere](../plan-auto-attendant-call-queue.md#prerequisites) Pianificare l'operatore automatico Teams e le code di chiamata per i prerequisiti quando si trasferiscono le chiamate a un numero di telefono esterno).

Tutti gli operatori automatici e le code di chiamata richiedono un account di risorsa associato. Gli account delle risorse che richiedono un numero di telefono devono avere una licenza *gratuita Microsoft Teams Telefono Standard – Utente* virtuale o una licenza utente *standard Teams Telefono* a pagamento prima di poter applicare un numero di telefono all'account della risorsa.

> [!TIP]
> Non è necessaria alcuna licenza per gli account delle risorse che verranno usati con operatori automatici annidati o code di chiamata a cui non è assegnato un numero di telefono. Per informazioni di riferimento, vedere il diagramma seguente.

:::image type="content" alt-text="Licenze per utenti virtuali." source="../media/resource-account.png":::

## <a name="virtual-user-license-allocation"></a>Assegnazione licenze utente virtuale

L'organizzazione è assegnata Microsoft Teams Telefono *licenze Standard - Utente* virtuale a seconda delle dimensioni complessive. Qualsiasi organizzazione con almeno una licenza con Teams Sistema telefonico, inclusi Teams Telefono Standard e Teams Telefono con licenze per il piano per chiamate, ha 25 licenze per utenti virtuali disponibili senza costi aggiuntivi. Quando si aggiungono 10 Teams Telefono Standard o Teams Telefono con licenze utente del piano per chiamate nell'organizzazione, diventa disponibile un'altra licenza Microsoft Teams Telefono *Standard -* Utente virtuale.

> [!NOTE]
> Teams Telefono Standard e Teams Telefono piano chiamate sono licenze per i componenti aggiuntivi disponibili per tutti Microsoft 365 abbonati. Teams Telefono licenze Standard sono incluse anche nell'ambito dei piani Microsoft 365 E5 standard.

Se l'organizzazione usa le licenze *Microsoft Teams Telefono Standard – Virtual User* gratuite per la creazione di nodi dell'operatore automatico o della coda di chiamata, è comunque possibile usare le licenze Teams Telefono *Standard* a pagamento con un account delle risorse. La maggior parte delle organizzazioni avrà un numero di licenze utente virtuale sufficiente in base al piano di scalabilità.

### <a name="license-allocation-example"></a>Esempio di assegnazione delle licenze

Contoso, Inc. ha acquistato 600 licenze che includono Sistema telefonico (una per ogni dipendente). A Contoso sono assegnate 25 licenze iniziali più 60 *Microsoft Teams Telefono standard - licenze* utente virtuale, 85 in totale. L'organizzazione ha 90 code di chiamata e operatori automatici con numeri di telefono. Devono assegnare tutte le licenze *Microsoft Teams Telefono Standard - Utente* virtuale e ottenere cinque licenze standard *Teams Telefono standard*.

Contoso dovrebbe prendere in considerazione la riprogettazione dell'operatore automatico e del sistema di coda di chiamata. Se usano meno numeri di telefono e più nodi annidati che non hanno bisogno di un numero di telefono, semplificano l'implementazione e riducono i costi.

## <a name="how-to-buy-microsoft-teams-phone-standard--virtual-user-licenses"></a>Come acquistare licenze Microsoft Teams Telefono Standard – Virtual User

1. Accedere all'interfaccia di amministrazione di Microsoft 365.
2. Passare a **BillingPurchase** >  **servicesAdd-ons** > .
3. Scorrere fino alla fine per trovare la licenza **Microsoft Teams Telefono Standard - Utente** virtuale. Seleziona **Acquista ora**.

   > [!NOTE]
   > Tenere presente che è comunque necessario **acquistare** la licenza anche se ha un costo pari a zero.

## <a name="change-an-existing-resource-account-to-use-a-microsoft-teams-phone-standard--virtual-user-license"></a>Modificare un account delle risorse esistente per usare una licenza Microsoft Teams Telefono Standard - Utente virtuale

Se si decide di cambiare la licenza dell'account delle risorse da una licenza *Teams Telefono Standard* a una licenza *Microsoft Teams Telefono Standard - Utente* virtuale:

1. Ottenere la nuova licenza Microsoft Teams Telefono Standard - Utente virtuale.
2. Seguire i passaggi collegati nel centro Amministrazione Microsoft 365 per [spostare gli utenti in un abbonamento diverso](/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription).

> [!WARNING]
> Rimuovere sempre una licenza *Teams Telefono Standard* e assegnare la licenza *Microsoft Teams Telefono Standard - Utente* virtuale nella stessa attività di licenza. Se si rimuove la vecchia licenza, si salvano le modifiche all'account, si aggiunge la nuova licenza e quindi si salvano di nuovo le impostazioni dell'account, l'account della risorsa potrebbe non funzionare più come previsto. In questo caso, è consigliabile creare un nuovo account delle risorse per la licenza *Microsoft Teams Telefono Standard - Utente* virtuale e rimuovere l'account delle risorse danneggiato.

## <a name="related-information"></a>Informazioni correlate

[Operatore automatico e servizio Code di chiamata](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521)

[Gestire gli account di risorsa in Microsoft Teams](../manage-resource-accounts.md)
