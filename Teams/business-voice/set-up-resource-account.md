---
title: Configurare un account Microsoft 365 Business Voice risorsa
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: Informazioni su come configurare un account Microsoft 365 Business Voice per l'uso con gli operatori automatici.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 76e91a650e9e72c21a39d292e32fe5ff8ecbf80b
ms.sourcegitcommit: 49cdcf344c63c805bcb6365804c6f5d1393e926a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2021
ms.locfileid: "52130376"
---
# <a name="step-4-set-up-a-business-voice-resource-account"></a>Passaggio 4: Configurare un account della risorsa Voce aziendale

In Microsoft Teams è necessario un account della risorsa per ogni operatore automatico o coda di chiamata. Agli account delle risorse possono essere assegnati anche numeri di telefono di servizio. In questo modo si assegnano i numeri di telefono agli operatori automatici e alle code di chiamata, consentendo ai chiamanti esterni Teams di raggiungere l'operatore automatico o la coda di chiamata.

## <a name="obtain-virtual-user-licenses"></a>Ottenere licenze utente virtuali

Gli account delle risorse richiedono una licenza per poter usare operatori automatici e code di chiamata. È possibile usare una licenza *Microsoft 365 Sistema telefonico - Utente* virtuale.

1. Accedere all'interfaccia di amministrazione di Microsoft 365.
2. Passare a **Componenti** aggiuntivi Servizi di  >    >  **acquisto fatturazione**  >  **Vedere tutti i prodotti aggiuntivi**
3. Scorrere fino alla fine per trovare la licenza **Microsoft 365 Sistema telefonico - Utente** virtuale. Seleziona **Dettagli**, quindi **Acquista**.
4. Nella pagina di acquisto della licenza selezionare il numero di licenze utente virtuali desiderate. È necessaria una licenza virtuale per ogni operatore automatico e coda di chiamata che si prevede di configurare. È consigliabile selezionare almeno cinque licenze per configurare più operatori automatici e code di chiamata in futuro senza dover acquistare subito altre licenze.
5. Deselezionare **Assegna automaticamente a tutti gli utenti senza licenze.**
6. Selezionare **Estrai adesso.**
7. Confermare l'ordine, **selezionare Avanti** e quindi **Eseguire l'ordine.**

> [!NOTE]
> Tenere presente che è comunque necessario  **acquistare** la licenza anche se ha un costo pari a zero.

## <a name="create-a-resource-account"></a>Creare un account della risorsa

Dopo aver ricevuto la licenza *Microsoft 365 Sistema telefonico - Utente* virtuale, è possibile creare l'account delle risorse.

![Screenshot dell'interfaccia utente per l'aggiunta di un account di risorsa](../media/resource-account-add.png)

1. Nell'Teams di amministrazione espandere **Impostazioni a** livello di organizzazione e quindi fare clic su **Account risorse.**
2. Selezionare **Aggiungi**.
3. Nel riquadro **Aggiungi account risorsa** compilare Nome **visualizzato** e quindi **Nome utente.** Scegliere un nome visualizzato descrittivo, ad esempio "Operatore automatico linea principale" per descrivere lo scopo dell'account della risorsa.
4. In **Tipo di account risorsa** selezionare **Operatore automatico.**
5. Selezionare **Salva**.

![Screenshot di un elenco di account delle risorse](../media/resource-accounts-page.png)

## <a name="assign-a-license"></a>Assegnare una licenza

Dopo aver creato l'account delle risorse, è necessario assegnare una licenza *Microsoft 365 Sistema telefonico -* Utente virtuale o Sistema telefonico *licenza.*

![Screenshot dell'interfaccia utente per l'assegnazione di licenze nell'interfaccia Microsoft 365 di amministrazione](../media/resource-account-assign-virtual-user-license.png)

1. Nell'Microsoft 365 di amministrazione passare a **Utenti**  >  **attivi**.
2. Selezionare l'account della risorsa.
1. Nella scheda **Licenze e app,** in **Licenze,** **selezionare Microsoft 365 Sistema telefonico - Utente virtuale**.
1. Selezionare **Salva modifiche** e quindi **Chiudi.**

## <a name="assign-a-service-number"></a>Assegnare un numero di servizio

![Screenshot dell'interfaccia utente assegna numero di servizio](../media/resource-account-assign-phone-number.png)

1. Nell'Teams di amministrazione passare a **Impostazioni a** livello di organizzazione e quindi Account **risorse.** 
1. Selezionare l'account della risorsa appena creato e quindi fare clic su **Assegna/annulla assegnazione.**
1. **Nell'elenco Telefono tipo di** numero scegliere **Online.**
1. Nella casella **Numero di telefono assegnato** cercare il numero da usare e fare clic su **Aggiungi.** Assicurarsi di includere il codice paese ,ad esempio **+1** 250 555 0012
1. Fare clic su **Salva**.
    > [!NOTE]
    > Non è necessario selezionare un operatore automatico **in** Assegna a perché l'operatore automatico a cui si vuole aggiungere il numero è già selezionato.

> [!div class="nextstepaction"]
> [Passaggio successivo: Assegnare numeri di telefono agli utenti](set-up-assign-numbers.md)
