---
title: 'Sistema telefonico-licenze per utenti virtuali '
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: waseemh
ms.topic: reference
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.custom:
- Licensing
- LIL_Placement
description: Informazioni sulle licenze gratuite degli utenti virtuali.
ms.openlocfilehash: 73edbae2fce7cdb2ed1fd5c499d58153d91e7086
ms.sourcegitcommit: 5f3c8ea2b3d68704885d212c8f2787c6bc7d1cf7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/25/2019
ms.locfileid: "36185122"
---
# <a name="phone-systemvirtual-user-license"></a>Sistema telefonico-licenza utente virtuale 

A partire dal 2 luglio 2019, un'organizzazione con un sistema telefonico con licenza gli utenti possono ora ottenere e assegnare un sistema telefonico gratuito-licenza utente virtuale o una licenza per l'utente del sistema telefonico a pagamento per gli account delle risorse. Non è più necessario un piano di chiamata. Tutti gli operatori automatici o le code di chiamata richiedono un account di risorse associato. Gli account delle risorse che necessitano di un numero di telefono necessitano di un sistema telefonico gratuito-licenza utente virtuale o una licenza per l'utente del sistema telefonico a pagamento prima di poter applicare un numero di telefono all'account delle risorse.

> [!TIP]
> Non è necessaria alcuna licenza per gli account delle risorse che verranno usati con gli operatori automatici annidati o le code di chiamata che non hanno un numero di telefono assegnato. Vedere il diagramma seguente per riferimento: 

![Licenze utente virtuali](../media/resource-account.png)

## <a name="virtual-user-license-allocation"></a>Assegnazione di licenze utente virtuale

L'organizzazione è assegnata al sistema telefonico-licenze utente virtuali a seconda della dimensione complessiva. Sono disponibili 25 licenze per gli utenti virtuali per qualsiasi organizzazione che disponga di almeno una licenza che includa il sistema telefonico o che abbia aggiunto un sistema telefonico. Quando si aggiungono 10 licenze utente del sistema telefonico nell'organizzazione, viene disponibile un altro sistema telefonico: la licenza per gli utenti virtuali.

> [!NOTE]
> Phone System è una licenza per il componente aggiuntivo disponibile con le licenze Office 365 F1, E1, E3 e Office Premium. Il sistema telefonico è incluso anche come parte delle licenze di Office 365 E5.

Se l'organizzazione usa il sistema telefonico gratuito disponibile, ossia le licenze utente virtuali nella creazione di nodi operatore automatico o coda di chiamata, è comunque possibile usare le licenze per il sistema telefonico a pagamento con un account delle risorse. La maggior parte delle organizzazioni avrà sufficienti licenze utente virtuali in base al piano di ridimensionamento. 

### <a name="license-allocation-example"></a>Esempio di allocazione della licenza

Contoso, Inc. ha acquistato le licenze 600 che includevano il sistema telefonico (uno per ogni dipendente), in modo che siano assegnate le licenze iniziali 25 e un altro sistema telefonico di 60. Contoso ha un totale di 85 sistema telefonico-licenze utente virtuali. La propria organizzazione ha code di chiamate di 90 e operatori automatici con numeri di telefono. Hanno bisogno di assegnare tutte le licenze per il sistema telefonico-utente virtuale e ottenere cinque licenze di sistema telefonico a prezzi regolari. 

Contoso dovrebbe valutare la possibilità di riprogettare l'operatore automatico e il sistema di accodamento delle chiamate per usare meno numeri di telefono e altri nodi annidati che non hanno bisogno di un numero di telefono o di una licenza. La rimozione di numeri di telefono non necessari semplifica l'implementazione e riduce i costi. 

## <a name="how-to-acquire-phone-systemvirtual-user-licenses"></a>Come acquistare il sistema telefonico-licenze utente virtuali 

1. Accedere all'interfaccia di amministrazione di Microsoft 365.
2. Accedere agli abbonamenti al**componente aggiuntivo** **fatturazione** > **Servizi** > di acquisto
3. Scorrere fino alla fine per trovare la licenza **"sistema telefonico-utente virtuale"** . Selezionare **Acquista ora**.

> [!WARNING]
> Tieni presente che hai ancora bisogno di **acquistare** la licenza anche se ha un costo pari a zero. 

## <a name="change-an-existing-resource-account-to-use-a-phone-systemvirtual-user-license"></a>Cambiare un account di risorse esistente per usare un sistema telefonico-licenza utente virtuale

Se si decide di cambiare le licenze per l'account delle risorse da una licenza di sistema telefonico a un sistema telefonico-licenza utente virtuale: 

1. Ottenere il nuovo sistema telefonico-licenza utente virtuale. 
2. Seguire i passaggi collegati nell'interfaccia di amministrazione di Microsoft 365 per [trasferire gli utenti a un altro abbonamento](https://docs.microsoft.com/en-us/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#move-users-to-a-different-subscription). 

> [!WARNING]
> Rimuovere sempre una licenza per il sistema telefonico completo e assegnare il sistema telefonico-licenza per gli utenti virtuali nella stessa attività di licenza. Se si rimuove la vecchia licenza, si salvano le modifiche dell'account, si aggiunge la nuova licenza e quindi si salvano di nuovo le impostazioni dell'account, l'account delle risorse potrebbe non funzionare più come previsto. In questo caso, è consigliabile creare un nuovo account delle risorse per il sistema telefonico-licenza utente virtuale e rimuovere l'account delle risorse interrotte. 

## <a name="related-information"></a>Informazioni correlate

[Aggiornamento del servizio di operatore automatico e code di chiamata](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521)

[Gestire gli account delle risorse in Microsoft Teams](../manage-resource-accounts.md)
