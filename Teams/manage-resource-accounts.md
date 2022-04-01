---
title: Gestire gli account delle risorse in Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jastark, wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.orgwidesettings.resourceaccounts.overview
- seo-marvel-apr2020
description: In questo articolo imparerai a creare, modificare e gestire gli account delle risorse in Microsoft Teams.
ms.openlocfilehash: cb89621d6049106cb090d72244644a4b14565657
ms.sourcegitcommit: 2388838163812eeabcbd5331aaf680b79da3ccba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2022
ms.locfileid: "64592711"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a>Gestire gli account di risorsa in Microsoft Teams

In Microsoft Teams è necessario un account di risorsa per ogni operatore automatico o coda di chiamata. Agli account delle risorse possono essere assegnati anche numeri di telefono di servizio. In questo modo si assegnano i numeri di telefono agli operatori automatici e alle code di chiamata, consentendo ai chiamanti esterni Teams di raggiungere l'operatore automatico o la coda di chiamata.

Questo articolo illustra come creare account delle risorse e prepararli per l'uso con operatori automatici e code di chiamata.

Prima di avviare le procedure descritte in questo articolo, verificare di aver eseguito le operazioni seguenti:

- [Ottenere licenze utente virtuali](#obtain-virtual-user-licenses)
- [Ottenere i numeri di servizio](#obtain-service-numbers)

> [!NOTE]
> Gli account delle risorse usati per gli operatori automatici e le code di chiamata sono disabilitati per l'accesso e devono rimanere invariati. La chat e la presenza non sono disponibili per questi account.

### <a name="obtain-virtual-user-licenses"></a>Ottenere licenze utente virtuali

Ogni account della risorsa richiede una licenza per lavorare con operatori automatici e code di chiamata. È possibile usare una licenza *Microsoft 365 Sistema telefonico - Utente* virtuale. Per ottenere queste licenze, vedere [Licenza utente virtuale](teams-add-on-licensing/virtual-user.md).

Verrà illustrato come assegnare la licenza a un account delle risorse più avanti in questo articolo.

Per ottenere la licenza per l'utente virtuale, nel interfaccia di amministrazione di Microsoft 365 passare a **BillingPurchase** >  **servicesAggiungere** >  gli abbonamenti e scorrere fino alla fine - verrà visualizzato *Sistema telefonico - Licenza* utente virtuale. Seleziona **Acquista ora**. Il costo è zero, ma è comunque necessario seguire questa procedura per acquisire la licenza.

### <a name="obtain-service-numbers"></a>Ottenere i numeri di servizio

I numeri di servizio sono facoltativi per gli operatori automatici e le code di chiamata, tuttavia è necessario almeno un numero di servizio per consentire ai chiamanti di raggiungere l'operatore automatico e la configurazione della coda di chiamata. Per qualsiasi operatore automatico o coda di chiamata che si vuole essere raggiungibile direttamente da un numero di servizio, è necessario avere un account della risorsa con un numero di servizio associato.

Gli account delle risorse possono usare numeri di servizio a numero verde o a numero verde. È possibile richiedere nuovi numeri o portarne di nuovi da un altro gestore.

Per ottenere nuovi numeri di servizio, vedere Ottenere [i numeri di telefono del servizio](getting-service-phone-numbers.md).

Per trasferire un numero da un altro gestore, vedere [Trasferire numeri di telefono Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).

## <a name="create-a-resource-account"></a>Creare un account della risorsa

È possibile creare un account delle risorse nell'Teams di amministrazione.

![Screenshot dell'interfaccia utente per l'aggiunta di un account di risorsa.](media/resource-account-add.png)

1. Nell'Teams di amministrazione espandere **Voce** e quindi fare clic su **Account risorse**.

2. Fare clic su **Aggiungi**.

3. Nel riquadro **Aggiungi account risorsa** compilare **Nome visualizzato**, **Nome utente** e tipo **di account risorsa**. Il tipo di account della risorsa **può essere** Operatore automatico o **Coda di** chiamata, a seconda della modalità di utilizzo dell'account della risorsa.

4. Fare clic su **Salva**.

![Screenshot di un elenco di account delle risorse.](media/resource-accounts-page.png)

## <a name="assign-a-license"></a>Assegnare una licenza

Per ogni account della risorsa, è necessario assegnare una *licenza Microsoft 365 Sistema telefonico - Utente* virtuale o *Sistema telefonico licenza.*

![Screenshot dell'interfaccia utente per l'assegnazione delle licenze nel interfaccia di amministrazione di Microsoft 365.](media/resource-account-assign-virtual-user-license.png)

1. Nella finestra interfaccia di amministrazione di Microsoft 365 fare clic sull'account della risorsa a cui si vuole assegnare una licenza.

2. Nella scheda **Licenze e app**, in **Licenze**, selezionare **Microsoft 365 Sistema telefonico - Utente virtuale**.

3. Fare clic su **Salva modifiche**.

## <a name="assign-a-service-number"></a>Assegnare un numero di servizio

Se si prevede di usare l'account della risorsa con un operatore automatico o una coda di chiamata che richiede un numero di servizio, assegnare un numero all'account della risorsa.

![Screenshot dell'interfaccia utente assegna numero di servizio.](media/resource-account-assign-phone-number.png)

1. Nella pagina Account risorse dell'interfaccia di amministrazione di Teams  selezionare l'account della risorsa a cui si vuole assegnare un numero di servizio e quindi fare clic su Assegna **/annulla assegnazione**.

2. **Nell'Telefono tipo di** numero scegliere il tipo di numero da usare.

3. Nella casella **Numero di telefono assegnato** cercare il numero da usare e fare clic su **Aggiungi**.

4. Fare clic su **Salva**.


Per assegnare un routing diretto o un numero ibrido a un account della risorsa, è necessario usare PowerShell:

```powershell
Set-CsPhoneNumberAssignment -Identity aa-contoso_main@contoso64.net -PhoneNumber +19295550150 -PhoneNumberType DirectRouting
```

## <a name="next-steps"></a>Passaggi successivi

Dopo aver completato la configurazione dell'account della risorsa e aver assegnato un numero di servizio, se necessario, è possibile usare l'account della risorsa con un operatore automatico o una coda di chiamata.

Vedere i riferimenti seguenti:

 - [Operatore automatico cloud](create-a-phone-system-auto-attendant.md)

 - [Coda di chiamata cloud](create-a-phone-system-call-queue.md)

È possibile modificare l'account della risorsa **Nome visualizzato** e **il tipo di account** risorsa usando l'opzione Modifica. Al **termine,** fare clic su Salva.

## <a name="change-an-existing-resource-account-to-use-a-virtual-user-license"></a>Modificare un account delle risorse esistente per usare una licenza utente virtuale

Se si decide di cambiare le licenze dell'account delle risorse esistenti da una licenza **di Sistema telefonico a** una licenza utente virtuale, è necessario acquisire la licenza utente virtuale gratuita e quindi seguire i passaggi del interfaccia di amministrazione di Microsoft 365 per spostare gli utenti in un altro [abbonamento.](/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription)

> [!WARNING]
> Rimuovere sempre una licenza Sistema telefonico completa e assegnare la licenza utente virtuale nella stessa attività di licenza. Se si rimuove la vecchia licenza, si salvano le modifiche all'account, si aggiunge la nuova licenza e quindi si salvano di nuovo le impostazioni dell'account, l'account della risorsa potrebbe non funzionare più come previsto. In questo caso, è consigliabile creare un nuovo account della risorsa per la licenza utente virtuale e rimuovere l'account della risorsa danneggiato.

## <a name="skype-for-business-server-2019"></a>Skype For Business Server 2019

Per gli account delle risorse ospitati in Skype For Business Server 2019 che possono essere usati con le code di chiamata cloud e gli operatori automatici cloud, vedere Pianificare le code di chiamata [cloud](/SkypeforBusiness/hybrid/plan-call-queue) o Pianificare gli operatori automatici [cloud](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant). Le implementazioni ibride (numeri ospitati nel routing diretto) vengono configurate usando il cmdlet [New-CsHybridApplicationEndpoint](/powershell/module/skype/new-cshybridapplicationendpoint) in un server Skype for Business Server 2019 locale.

Gli ID applicazione da usare durante la creazione delle istanze dell'applicazione sono:

- **Operatore automatico:** ce933385-9390-45d1-9512-c8d228074e07
- **Coda di chiamata:** 11cd3e2e-fccb-42ad-ad00-878b93575e07

> [!NOTE]
> Se si vuole che la coda di chiamata o l'operatore automatico sia ricercabile dagli utenti di Skype For Business Server 2019, è consigliabile creare gli account delle risorse in Skype For Business Server 2019, poiché gli account delle risorse online non vengono sincronizzati con Active Directory. Quando i record DNS SRV per sipfederationtls si risolvono Skype for Business Server 2019, gli account delle risorse  devono essere creati in Skype For Business Server 2019 con SfB Management Shell e sincronizzati con Azure AD.

Per le implementazioni ibride con Skype for Business Server:

   [Pianificare gli operatori automatici cloud](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)
  
   [Pianificare le code delle chiamate cloud](/SkypeforBusiness/hybrid/plan-call-queue)
   
   [Configurare gli account delle risorse locali](/SkypeForBusiness/hybrid/configure-onprem-ra)


## <a name="delete-a-resource-account"></a>Eliminare un account della risorsa

Assicurarsi di dissociare il numero di telefono dall'account della risorsa prima di eliminarlo, per evitare che il numero di servizio venga bloccato in modalità in sospeso.

Dopo aver fatto questo, è possibile eliminare l'account della risorsa nella interfaccia di amministrazione di Microsoft 365, nella scheda Utenti.

Per disassociare un numero di telefono di routing diretto dall'account della risorsa, usare il cmdlet seguente:

```powershell
Remove-CsPhoneNumberAssignment -Identity <Resource Account Object ID> -PhoneNumber <assigned phone number> -PhoneNumberType DirectRouting
```
