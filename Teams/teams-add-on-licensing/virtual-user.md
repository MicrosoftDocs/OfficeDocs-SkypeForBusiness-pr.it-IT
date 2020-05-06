---
title: Sistema telefonico Microsoft 365-licenze utente virtuali
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
description: Informazioni su come assegnare un sistema telefonico gratuito-licenza per gli utenti virtuali o una licenza per l'utente del sistema telefonico a pagamento per gli account delle risorse dell'organizzazione.
ms.openlocfilehash: cd70b4a1d24bf762c5aa1508d29a9ce343cf4b76
ms.sourcegitcommit: 09ff11f8e4f6a93cedc34a5d732a133163df79a0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "44042413"
---
# <a name="microsoft-365-phone-system--virtual-user-license"></a>Microsoft 365 Phone System-licenza per utenti virtuali

Organizzazioni con sistema telefonico gli utenti con licenza possono assegnare un sistema telefonico gratuito Microsoft 365-licenza utente virtuale o una licenza per l'utente del sistema telefonico a pagamento per gli account delle risorse. Non è necessario un piano di chiamata. Tutti gli operatori automatici o le code di chiamata richiedono un account di risorse associato. Gli account delle risorse che richiedono un numero di telefono necessitano di un sistema telefonico gratuito Microsoft 365-licenza utente virtuale o una licenza per l'utente del sistema telefonico a pagamento prima di poter applicare un numero di telefono all'account delle risorse.

> [!TIP]
> Non è necessaria alcuna licenza per gli account delle risorse che verranno usati con gli operatori automatici annidati o le code di chiamata che non hanno un numero di telefono assegnato. Vedere il diagramma seguente per riferimento: 

![Licenze utente virtuali](../media/resource-account.png)

## <a name="virtual-user-license-allocation"></a>Assegnazione di licenze utente virtuale

L'organizzazione è assegnata al sistema telefonico Microsoft 365-licenze utente virtuali a seconda della dimensione complessiva. Qualsiasi organizzazione che disponga di almeno una licenza, incluso il sistema telefonico o il sistema telefonico, ha aggiunto 25 licenze per gli utenti virtuali a costo zero. Quando si aggiungono 10 licenze utente del sistema telefonico nell'organizzazione, viene disponibile un altro sistema telefonico Microsoft 365-licenza per gli utenti virtuali.

> [!NOTE]
> Phone System è una licenza per il componente aggiuntivo disponibile con Microsoft 365 e Office 365 E1 ed E3. Il sistema telefonico è incluso anche nelle licenze Microsoft 365 E5, Office 365 E5 e Microsoft 365 Business Voice.

Se l'organizzazione usa il sistema telefonico disponibile gratuito Microsoft 365-licenze per gli utenti virtuali nella creazione di nodi operatore automatico o coda di chiamata, è comunque possibile usare le licenze per il sistema telefonico a pagamento con un account di risorse. La maggior parte delle organizzazioni avrà sufficienti licenze utente virtuali in base al piano di ridimensionamento. 

### <a name="license-allocation-example"></a>Esempio di allocazione della licenza

Contoso, Inc. ha acquistato le licenze 600 che includevano il sistema telefonico (uno per ogni dipendente). Contoso è assegnato un sistema telefonico di 25 Plus 60 Microsoft 365-licenze per gli utenti virtuali, 85 in totale. La propria organizzazione ha code di chiamate di 90 e operatori automatici con numeri di telefono. È necessario assegnare tutti i sistemi telefonici Microsoft 365-licenze per gli utenti virtuali e ottenere cinque licenze di sistema telefonico a prezzi regolari. 

Contoso dovrebbe valutare la possibilità di riprogettare l'operatore automatico e il sistema delle code di chiamata. Se usano meno numeri di telefono e altri nodi annidati che non hanno bisogno di un numero di telefono, semplificano l'implementazione e riducono i costi. 

## <a name="how-to-buy-microsoft-365-phone-system--virtual-user-licenses"></a>Come acquistare Microsoft 365 Phone System-Virtual User licenses 

1. Accedere all'interfaccia di amministrazione di Microsoft 365.
2. Accedere ai**componenti aggiuntivi** per l'**acquisto di servizi** > di **fatturazione** > 
3. Scorrere fino alla fine per trovare il **sistema telefonico Microsoft 365-** licenza per gli utenti virtuali. Selezionare **Acquista ora**.

> [!NOTE]
> Tieni presente che devi comunque **acquistare** la licenza anche se ha un costo pari a zero. 

## <a name="change-an-existing-resource-account-to-use-a-microsoft-365-phone-system--virtual-user-license"></a>Cambiare un account di risorse esistente per usare un sistema telefonico Microsoft 365-licenza utente virtuale

Se si decide di cambiare la licenza per l'account delle risorse da una licenza di sistema telefonico a un sistema telefonico Microsoft 365-licenza utente virtuale: 

1. Ottenere il nuovo sistema telefonico Microsoft 365-licenza per gli utenti virtuali. 
2. Seguire i passaggi collegati nell'interfaccia di amministrazione di Microsoft 365 per [trasferire gli utenti a un altro abbonamento](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#move-users-to-a-different-subscription). 

> [!WARNING]
> Rimuovere sempre una licenza per il sistema telefonico completo e assegnare il sistema telefonico Microsoft 365-licenza per gli utenti virtuali nella stessa attività di licenza. Se si rimuove la vecchia licenza, si salvano le modifiche dell'account, si aggiunge la nuova licenza e quindi si salvano di nuovo le impostazioni dell'account, l'account delle risorse potrebbe non funzionare più come previsto. In questo caso, è consigliabile creare un nuovo account delle risorse per il sistema telefonico Microsoft 365-licenza per gli utenti virtuali e rimuovere l'account delle risorse interrotte. 

## <a name="related-information"></a>Informazioni correlate

[Aggiornamento del servizio di operatore automatico e code di chiamata](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521)

[Gestire gli account di risorsa in Microsoft Teams](../manage-resource-accounts.md)
