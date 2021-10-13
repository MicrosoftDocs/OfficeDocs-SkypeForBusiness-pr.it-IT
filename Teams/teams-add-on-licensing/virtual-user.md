---
title: Microsoft 365 Sistema telefonico - Licenze utente virtuale
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
description: Informazioni su come assegnare una licenza Sistema telefonico utente virtuale o una licenza utente Sistema telefonico a pagamento agli account delle risorse dell'organizzazione.
ms.openlocfilehash: f0a26c03a5654a3f2df9538fe8bbb74c4a5b58e4
ms.sourcegitcommit: 11882e93618b8d69d21586c7b1f6a4460b96dd7d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2021
ms.locfileid: "60283000"
---
# <a name="microsoft-365-phone-system--virtual-user-license"></a>Microsoft 365 Sistema telefonico - Licenza utente virtuale

Le organizzazioni con Sistema telefonico con licenza possono assegnare una licenza Microsoft 365 Sistema telefonico - Utente virtuale gratuita o una licenza Sistema telefonico utente a pagamento agli account delle risorse. Un piano per le chiamate non è sempre necessario [(vedere](../plan-auto-attendant-call-queue.md#prerequisites) Pianificare l'operatore automatico Teams e le code di chiamata per i prerequisiti quando si trasferiscono le chiamate a un numero di telefono esterno). Tutti gli operatori automatici o le code di chiamata richiedono un account di risorsa associato. Gli account delle risorse che richiedono un numero di telefono devono avere una licenza Microsoft 365 Sistema telefonico - Utente virtuale o una licenza utente Sistema telefonico a pagamento prima di poter applicare un numero di telefono all'account della risorsa.

> [!TIP]
> Non è necessaria alcuna licenza per gli account delle risorse che verranno usati con operatori automatici annidati o code di chiamata a cui non è assegnato un numero di telefono. Per informazioni di riferimento, vedere il diagramma seguente.

:::image type="content" alt-text="Licenze per utenti virtuali." source="../media/resource-account.png":::

## <a name="virtual-user-license-allocation"></a>Assegnazione licenze utente virtuale

L'organizzazione è assegnata Microsoft 365 Sistema telefonico licenze utente virtuale a seconda delle dimensioni complessive. Tutte le organizzazioni che hanno almeno una licenza Sistema telefonico o che Sistema telefonico sono state aggiunte hanno 25 licenze utente virtuale disponibili senza costi aggiuntivi. Quando si aggiungono 10 Sistema telefonico licenze utente nell'organizzazione, viene Microsoft 365 Sistema telefonico una licenza utente virtuale.

> [!NOTE]
> Sistema telefonico è una licenza per componenti aggiuntivi disponibile con Microsoft 365 e Office 365 E1 ed E3. Sistema telefonico è incluso anche come parte delle Microsoft 365 E5, Office 365 E5 e Microsoft 365 Business Voice licenze.

Se l'organizzazione usa le licenze Microsoft 365 Sistema telefonico - Virtual User disponibili per la creazione di nodi dell'operatore automatico o della coda di chiamata, è comunque possibile usare le licenze di sistema Telefono a pagamento con un account delle risorse. La maggior parte delle organizzazioni avrà un numero di licenze utente virtuale sufficiente in base al piano di scalabilità. 

### <a name="license-allocation-example"></a>Esempio di assegnazione delle licenze

Contoso, Inc. ha acquistato 600 licenze che includevano Sistema telefonico (una per ogni dipendente). A Contoso sono assegnate 25 licenze iniziali più 60 Microsoft 365 Sistema telefonico - Licenze utente virtuale, 85 in totale. L'organizzazione ha 90 code di chiamata e operatori automatici con numeri di telefono. Devono assegnare tutte le licenze Microsoft 365 Sistema telefonico - Utente virtuale e ottenere cinque licenze Sistema telefonico a prezzo normale.

Contoso dovrebbe prendere in considerazione la riprogettazione dell'operatore automatico e del sistema di coda di chiamata. Se usano meno numeri di telefono e più nodi annidati che non hanno bisogno di un numero di telefono, semplificano l'implementazione e riducono i costi.

## <a name="how-to-buy-microsoft-365-phone-system--virtual-user-licenses"></a>Come acquistare Microsoft 365 Sistema telefonico - Licenze utente virtuale

1. Accedere all'interfaccia di amministrazione di Microsoft 365.
2. Passare a **Componenti** aggiuntivi Servizi di acquisto  >    >  **fatturazione**
3. Scorrere fino alla fine per trovare la licenza **Microsoft 365 Sistema telefonico - Utente** virtuale. Seleziona **Acquista ora**.

   > [!NOTE]
   > Tenere presente che è comunque necessario **acquistare** la licenza anche se ha un costo pari a zero.

## <a name="change-an-existing-resource-account-to-use-a-microsoft-365-phone-system--virtual-user-license"></a>Modificare un account delle risorse esistente per usare una licenza Microsoft 365 Sistema telefonico - Utente virtuale

Se si decide di cambiare la licenza dell'account delle risorse da una licenza Sistema telefonico a una licenza Microsoft 365 Sistema telefonico - Utente virtuale:

1. Ottenere la nuova licenza Microsoft 365 Sistema telefonico - Utente virtuale.
2. Seguire i passaggi collegati nel centro Amministrazione Microsoft 365 per [spostare gli utenti in un abbonamento diverso.](/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription)

> [!WARNING]
> Rimuovere sempre una licenza Sistema telefonico completa e assegnare la licenza Microsoft 365 Sistema telefonico - Utente virtuale nella stessa attività di licenza. Se si rimuove la vecchia licenza, si salvano le modifiche all'account, si aggiunge la nuova licenza e quindi si salvano di nuovo le impostazioni dell'account, l'account della risorsa potrebbe non funzionare più come previsto. In questo caso, è consigliabile creare un nuovo account delle risorse per la licenza Microsoft 365 Sistema telefonico - Utente virtuale e rimuovere l'account delle risorse danneggiato. 

## <a name="related-information"></a>Informazioni correlate

[Operatore automatico e servizio Code di chiamata](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521)

[Gestire gli account di risorsa in Microsoft Teams](../manage-resource-accounts.md)
