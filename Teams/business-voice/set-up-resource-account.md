---
title: Configurare un account Telefono di Microsoft Teams di sistema
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
ms.localizationpriority: medium
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: Informazioni su come configurare un account Telefono di Microsoft Teams di sistema per l'uso con gli operatori automatici.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7764d6b7f7d09cd2c5065ab24e73cb0fdec9c5c6
ms.sourcegitcommit: cbdc80c302e97d18a923ef57bb5d4b6cf7676d00
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/30/2022
ms.locfileid: "64556547"
---
# <a name="step-4-set-up-a-teams-phone-system-resource-account"></a>Passaggio 4: Configurare un account Teams Sistema telefonico risorsa

Gli account delle risorse non sono assegnati a un utente specifico. Gli account delle risorse, che usano una licenza utente virtuale gratuita, vengono invece usati dai dispositivi e dai servizi in Microsoft 365. In Microsoft Teams, agli account delle risorse vengono assegnati numeri di telefono e quindi associati agli operatori automatici e alle code di chiamata.

Associando gli account delle risorse agli operatori automatici e alle code di chiamata, è possibile aggiungere uno o più numeri a numero verde o a pedaggio. Ad esempio, è possibile associare un account della risorsa a un numero a pedaggio a un operatore automatico per i chiamanti locali. Per le chiamate interurbane, è possibile associare un altro account della risorsa a un numero verde allo stesso operatore automatico.

Le sezioni di questo articolo illustrano come configurare un account della risorsa e quindi assegnare un numero di telefono. In seguito, l'account della risorsa verrà associato a un operatore automatico.

## <a name="obtain-virtual-user-licenses"></a>Ottenere licenze utente virtuali

Gli account delle risorse richiedono una licenza per poter usare operatori automatici e code di chiamata. È possibile usare una licenza *Telefono di Microsoft Teams standard - utente* virtuale.

> [!NOTE]
> È consigliabile eseguire la procedura seguente solo se si è effettuato l'accesso a un Teams Telefono con il periodo di valutazione della licenza del bundle piano per chiamate. Se hai acquistato Teams Telefono con le licenze del bundle piano per chiamate, le licenze virtuali dovrebbero essere già applicate al tuo account.
>
> Per verificare se si hanno già licenze virtuali, accedere Microsoft 365 un account con autorizzazioni di amministratore globale. Quindi vai a Fatturazione > [I tuoi prodotti](https://admin.microsoft.com/Adminportal/Home#/subscriptions). Se si hanno licenze virtuali, verranno visualizzate come **Telefono di Microsoft Teams Standard - Utente virtuale**.

1. Aprire il interfaccia di amministrazione di Microsoft 365 e accedere con un utente amministratore globale. In genere si tratta dell'account usato per iscriversi per Microsoft 365.
2. Nel riquadro di spostamento sinistro passare a <a href="https://admin.microsoft.com/Adminportal/Home#/catalog" target="_blank">**BillingPurchase** > </a> **servicesAdd-onsee** >  >  **all Add-onsee all Add-ons products**.
3. Scorrere fino alla fine per trovare la licenza **Telefono di Microsoft Teams Standard - Utente** virtuale. Seleziona **Dettagli**, quindi **Acquista**.
4. Nella pagina di acquisto della licenza selezionare il numero di licenze utente virtuali desiderate. È necessaria una licenza virtuale per ogni operatore automatico e coda di chiamata che si prevede di configurare. È consigliabile selezionare almeno cinque licenze per configurare più operatori automatici e code di chiamata in futuro senza dover acquistare subito altre licenze.
5. Deselezionare **Assegna automaticamente a tutti gli utenti senza licenze**.
6. Seleziona **Estrai ora**.
7. Confermare l'ordine, **selezionare Avanti** e quindi **Eseguire l'ordine**.

> [!NOTE]
> Tenere presente che è comunque necessario  **acquistare** la licenza anche se ha un costo pari a zero.

## <a name="create-a-resource-account"></a>Creare un account della risorsa

Dopo aver ricevuto la licenza *Telefono di Microsoft Teams Standard - Utente* virtuale, è possibile creare l'account delle risorse.

1. Aprire l'Microsoft Teams di amministrazione e accedere con un utente che è un amministratore globale (in genere si tratta dell'account usato per iscriversi per Microsoft 365).
2. Nel riquadro di spostamento sinistro passare a <a href="https://admin.teams.microsoft.com/company-wide-settings/resource-accounts" target="_blank">**Account VoiceResource** > </a>.
3. Selezionare **Aggiungi**.
4. Nel riquadro **Aggiungi account risorsa** compilare **Nome visualizzato** e quindi Nome **utente**. Scegliere un nome visualizzato descrittivo, ad esempio "Operatore automatico linea principale" per descrivere lo scopo dell'account della risorsa.
5. In **Tipo di account risorsa** selezionare **Operatore automatico**.
6. Selezionare **Salva**.

## <a name="assign-a-license"></a>Assegnare una licenza

Dopo aver creato l'account delle risorse, è necessario assegnare una licenza *Telefono di Microsoft Teams Standard - Utente* virtuale o Teams Telefono *licenza Standard*.

1. Aprire il interfaccia di amministrazione di Microsoft 365 e accedere con un utente amministratore globale. In genere si tratta dell'account usato per iscriversi per Microsoft 365.
1. Nel riquadro di spostamento sinistro passare a <a href="https://admin.microsoft.com/Adminportal/Home#/users" target="_blank">**UtentiAttivi** > </a> utenti.
1. Selezionare l'account della risorsa.
1. Nella scheda **Licenze e app**, in **Licenze**, selezionare Telefono di Microsoft Teams **Standard - Utente virtuale**.
1. Selezionare **Salva modifiche** e quindi **Chiudi**.

## <a name="assign-a-service-number"></a>Assegnare un numero di servizio

![Screenshot dell'interfaccia utente assegna numero di servizio.](../media/resource-account-assign-phone-number.png)

1. Aprire l'Microsoft Teams di amministrazione e accedere con un utente che è un amministratore globale (in genere si tratta dell'account usato per iscriversi per Microsoft 365).
1. Nel riquadro di spostamento sinistro passare a <a href="https://admin.teams.microsoft.com/company-wide-settings/resource-accounts" target="_blank">**Account VoiceResource** > </a>.
1. Selezionare l'account della risorsa appena creato e quindi fare clic su **Assegna/annulla assegnazione**.
1. **Nell'Telefono tipo di numero scegliere** **Online**.
1. Nella casella **Numero di telefono assegnato** cercare il numero da usare e fare clic su **Aggiungi**. Assicurarsi di includere il codice paese, ad esempio **+1** 250 555 0012.
1. Fare clic su **Salva**.

> [!div class="nextstepaction"]
> [Passaggio successivo: Assegnare numeri di telefono agli utenti](set-up-assign-numbers.md)
