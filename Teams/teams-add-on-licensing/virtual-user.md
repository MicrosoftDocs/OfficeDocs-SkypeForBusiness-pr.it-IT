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
- admindeeplinkMAC
description: Informazioni su come assegnare licenze Telefono di Microsoft Teams Account risorse agli account delle risorse per gli operatori automatici e le code di chiamata nell'organizzazione.
ms.openlocfilehash: 56b461c2de32f32dd51d72c5468e31f51b107310
ms.sourcegitcommit: 09b77e83bc41914007606468e322d4ea47e2e8a4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/08/2022
ms.locfileid: "67630426"
---
# <a name="microsoft-teams-phone-resource-account-licenses"></a>licenze dell'account risorse di Telefono di Microsoft Teams

In Microsoft Teams, tutti gli operatori automatici e le code di chiamata richiedono un account di risorse associato. A ogni account di risorsa deve essere assegnata una licenza **Telefono di Microsoft Teams Account risorse** per assicurarsi che siano correttamente identificati dal sistema e funzionino correttamente, *indipendentemente dal fatto che all'account della risorsa venga assegnato un numero di telefono*. Alle organizzazioni con un abbonamento che include Teams Phone viene assegnato automaticamente un determinato numero di licenze **per l'account di risorse del telefono di Teams** senza costi aggiuntivi.  Un piano per chiamate Microsoft non è necessario a meno che non si voglia essere in grado di effettuare chiamate in uscita con tale account di risorsa. Per altre informazioni, vedere [Pianificare l'operatore automatico di Teams e le code di chiamata](../plan-auto-attendant-call-queue.md#prerequisites).

> [!NOTE]
> In precedenza, una licenza **per l'account di risorse del telefono di Teams** (una volta nota come licenza **utente virtuale** ) era necessaria solo quando si assegnava un numero di telefono a un account di risorse. Ora, a tutti gli account delle risorse deve essere assegnata una licenza **Account risorse di Teams Phone** , indipendentemente dal fatto che gli venga assegnato o meno un numero di telefono. Inoltre, non assegnare una licenza **di Teams Phone Standard** a un account della risorsa. Se gli account delle risorse sono configurati con licenze **di Teams Phone Standard**, è necessario passare a una licenza **Account di risorse di Teams Phone** come descritto di seguito.
 

## <a name="resource-account-license-allocation"></a>Allocazione licenze account risorsa

All'organizzazione sono assegnate licenze **per l'account di risorse del telefono di Teams** in base alle dimensioni complessive. A tutte le organizzazioni che hanno un abbonamento con funzionalità Sistema telefonico, ad esempio **Teams Phone Standard** e **Teams Phone con licenze per il piano per** chiamate, vengono assegnate 25 licenze **per l'account delle risorse del telefono di Teams** disponibili gratuitamente. 

Per ogni 10 licenze utente di **Teams Phone Standard** o **Teams Phone con piano per chiamate** nell'organizzazione, diventa disponibile un'altra licenza **Account risorse di Teams Phone**.  La maggior parte delle organizzazioni avrà un numero sufficiente di licenze **per l'account delle risorse del telefono di Teams** in base a questo piano di ridimensionamento. Nel caso in cui siano necessarie altre licenze **per l'account di risorse del telefono di Teams** , è possibile acquistare altre licenze **per l'account di risorse del telefono di Teams** oltre l'allocazione standard tramite il rappresentante dell'account Microsoft.

### <a name="license-allocation-example"></a>Esempio di assegnazione delle licenze

Contoso, Inc. ha acquistato 600 licenze che includono Sistema telefonico (una per ogni dipendente). A Contoso viene assegnata una licenza iniziale di 25 più 60 **account di risorse di Teams Phone** , 85 in totale. L'organizzazione ha 90 code di chiamata e operatori automatici. Devono assegnare tutte le licenze **dell'account di risorse del telefono di Teams** e acquistare cinque licenze aggiuntive per **l'account di risorse del telefono di Teams** . 

## <a name="how-to-obtain-microsoft-teams-phone-resource-account-licenses"></a>Come ottenere licenze per Telefono di Microsoft Teams account risorse

1. Accedere alla [interfaccia di amministrazione di Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=2024339).
2. Passare a **Componenti aggiuntivi** [**per l'acquisto di servizi**](https://go.microsoft.com/fwlink/p/?linkid=868433) >  di **fatturazione** > .
3. Scorrere per trovare la licenza **Telefono di Microsoft Teams Account risorse**. Seleziona **Acquista ora**.

   > [!NOTE]
   > Tenere presente che, anche se si è all'interno dell'allocazione, è comunque necessario **acquistare** la licenza anche se il costo è zero.

## <a name="change-an-existing-resource-account-to-use-a-microsoft-teams-phone-resource-account-license"></a>Modificare un account di risorse esistente per usare una licenza Telefono di Microsoft Teams Account risorse

Se si hanno account di risorse esistenti che usano una licenza **di Teams Phone Standard**, è necessario passare a usare una licenza **Account risorse di Teams Phone**:

1. Ottieni la nuova licenza **account di risorse di Teams Phone** .
2. Seguire i passaggi collegati nella interfaccia di amministrazione di Microsoft 365 [spostare gli utenti in un abbonamento diverso](/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription).

> [!WARNING]
> Rimuovere sempre una licenza **di Teams Phone Standard** e assegnare la licenza **Account risorse del telefono di Teams** nella stessa attività di licenza. Se rimuovi la vecchia licenza, salvi le modifiche dell'account, aggiungi la nuova licenza e salvi di nuovo le impostazioni dell'account, l'account della risorsa potrebbe non funzionare più come previsto, come gli operatori automatici e le code di chiamata della tua organizzazione non funzionano più.
>
> In questo caso, è consigliabile creare un nuovo account di risorsa usando la licenza **Account risorse di Teams Phone** e rimuovere l'account delle risorse danneggiato.

## <a name="related-information"></a>Informazioni correlate

[Aggiornamento del servizio Operatore automatico e code di chiamata](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521)

[Gestire gli account di risorsa in Microsoft Teams](../manage-resource-accounts.md)
