---
title: licenze dell'account risorse di Telefono di Microsoft Teams
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
description: Informazioni su come assegnare licenze gratuite dell'account telefonico di Teams o licenze utente a pagamento Teams Phone Standard agli account delle risorse nell'organizzazione.
ms.openlocfilehash: 07b47b2ec5b24b1edbfb599dc5a61e96169a02a2
ms.sourcegitcommit: a6f4c459b9c8154814a8a5b098bde1e374348c99
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/05/2022
ms.locfileid: "66615402"
---
# <a name="microsoft-teams-phone-resource-account-licenses"></a>licenze dell'account risorse di Telefono di Microsoft Teams

Le organizzazioni con Teams Phone Standard o Teams Phone con piano per chiamate con licenza possono assegnare una licenza gratuita *Telefono di Microsoft Teams Resource Account* o una licenza utente *Teams Phone Standard* a pagamento agli account delle risorse. Un piano per chiamate Microsoft non è sempre necessario (vedi [Pianificare l'operatore automatico di Teams e le code di chiamata](../plan-auto-attendant-call-queue.md#prerequisites) per i prerequisiti durante il trasferimento delle chiamate a un numero di telefono esterno).

Tutti gli operatori automatici e le code di chiamata richiedono un account di risorse associato. Gli account delle risorse che richiedono un numero di telefono devono avere una licenza gratuita *Telefono di Microsoft Teams Account risorse* o una licenza utente *a pagamento Teams Phone Standard* prima di poter applicare un numero di telefono all'account della risorsa.

> [!TIP]
> Non è necessaria alcuna licenza per gli account delle risorse che verranno usati con operatori automatici annidati o code di chiamata a cui non è assegnato un numero di telefono. Per informazioni di riferimento, vedere il diagramma seguente.

## <a name="resource-account-license-allocation"></a>Allocazione licenze account risorsa

All'organizzazione viene assegnata *Telefono di Microsoft Teams licenze per l'account delle* risorse, a seconda delle dimensioni complessive. Qualsiasi organizzazione che abbia almeno una licenza con le funzionalità di Sistema telefonico di Teams, inclusi Teams Phone Standard e Teams Phone con licenze piano per chiamate, ha 25 licenze di Account risorse disponibili gratuitamente. Quando aggiungi 10 Teams Phone Standard o Teams Phone con licenze utente per il piano per chiamate nella tua organizzazione, diventa disponibile un'altra *licenza Telefono di Microsoft Teams account risorse*.

> [!NOTE]
> Teams Phone Standard e Teams Phone con piano per chiamate sono licenze per componenti aggiuntivi disponibili per tutti gli abbonati a Microsoft 365. Teams Phone Standard licenze sono incluse anche nei piani di Microsoft 365 E5.

Se l'organizzazione utilizza le licenze gratuite *per l'account di risorsa Telefono di Microsoft Teams* per la creazione di nodi dell'operatore automatico o della coda di chiamata, è comunque possibile usare le licenze *di Teams Phone Standard* a pagamento con un account di risorse. La maggior parte delle organizzazioni avrà licenze account risorse sufficienti in base al piano di ridimensionamento.

### <a name="license-allocation-example"></a>Esempio di assegnazione delle licenze

Contoso, Inc. ha acquistato 600 licenze che includono Sistema telefonico (una per ogni dipendente). A Contoso viene assegnata una licenza iniziale di 25 più 60 *Telefono di Microsoft Teams account risorse*, di cui 85 in totale. L'organizzazione ha 90 code di chiamata e operatori automatici con numeri di telefono. Devono assegnare tutte le licenze *Telefono di Microsoft Teams Account risorse* e ottenere cinque licenze *Teams Phone Standard* a prezzo normale.

Contoso dovrebbe prendere in considerazione la riprogettazione del sistema dell'operatore automatico e della coda di chiamata. Se usano meno numeri di telefono e più nodi annidati che non richiedono un numero di telefono, semplificano l'implementazione e riducono i costi.

## <a name="how-to-buy-microsoft-teams-phone-resource-account-licenses"></a>Come acquistare licenze per Telefono di Microsoft Teams account delle risorse

1. Accedere all'interfaccia di amministrazione di Microsoft 365.
2. Passare a **Componenti aggiuntivi** **per l'acquisto di servizi** >  di **fatturazione** > .
3. Scorrere per trovare la licenza **Telefono di Microsoft Teams Account risorse**. Seleziona **Acquista ora**.

   > [!NOTE]
   > Tenere presente che è necessario **acquistare** la licenza anche se ha un costo pari a zero.

## <a name="change-an-existing-resource-account-to-use-a-microsoft-teams-phone-resource-account-license"></a>Modificare un account di risorse esistente per usare una licenza Telefono di Microsoft Teams Account risorse

Se si decide di cambiare la licenza dell'account delle risorse da una licenza *di Teams Phone Standard* a una *licenza Telefono di Microsoft Teams account risorsa*:

1. Ottenere la nuova licenza *account di Telefono di Microsoft Teams risorsa*.
2. Seguire i passaggi collegati nella interfaccia di amministrazione di Microsoft 365 [spostare gli utenti in un abbonamento diverso](/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription).

> [!WARNING]
> Rimuovere sempre una licenza *di Teams Phone Standard* completa e assegnare la licenza *Telefono di Microsoft Teams Account risorse* nella stessa attività di licenza. Se si rimuove la licenza precedente, si salvano le modifiche dell'account, si aggiunge la nuova licenza e quindi si salvano di nuovo le impostazioni dell'account, l'account della risorsa potrebbe non funzionare più come previsto. In questo caso, è consigliabile creare un nuovo account per le risorse per la licenza *Account risorse di Telefono di Microsoft Teams* e rimuovere l'account delle risorse danneggiato.

## <a name="related-information"></a>Informazioni correlate

[Aggiornamento del servizio Operatore automatico e code di chiamata](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521)

[Gestire gli account di risorsa in Microsoft Teams](../manage-resource-accounts.md)
