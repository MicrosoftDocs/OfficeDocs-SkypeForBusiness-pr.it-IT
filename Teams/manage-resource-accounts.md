---
title: Gestire gli account delle risorse in Teams
ms.author: mikeplum
author: MikePlumleyMSFT
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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.orgwidesettings.resourceaccounts.overview
- seo-marvel-apr2020
description: In questo articolo imparerai a creare, modificare e gestire gli account delle risorse in Microsoft Teams.
ms.openlocfilehash: 2a043b608dfe311003dea26acc8a0c236460fad5
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031022"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a>Gestire gli account di risorsa in Microsoft Teams

Un account delle risorse è un oggetto utente disabilitato in Azure AD e può essere usato per rappresentare le risorse in generale. Ad esempio, un account della risorsa può essere usato in Exchange per rappresentare le sale riunioni e consentire loro di avere un numero di telefono e un calendario. Un account delle risorse può essere installato in Microsoft 365 o in locale utilizzando Skype for Business Server 2019.

In Microsoft Teams è necessario un account della risorsa per ogni operatore automatico o coda di chiamata. Agli account delle risorse possono essere assegnati anche numeri di telefono di servizio. In questo modo, è possibile assegnare numeri di telefono agli operatori automatici e alle code di chiamata, consentendo ai chiamanti dall'esterno di Teams di raggiungere l'operatore automatico o la coda di chiamata.

Questo articolo illustra come creare account delle risorse e prepararli per l'uso con operatori automatici e code di chiamata.

Prima di iniziare le procedure descritte in questo articolo, assicurarsi di aver eseguito le operazioni seguenti:

- [Ottenere licenze utente virtuali](#obtain-virtual-user-licenses)
- [Ottenere numeri di servizio](#obtain-service-numbers)

### <a name="obtain-virtual-user-licenses"></a>Ottenere licenze utente virtuali

Ogni account delle risorse richiede una licenza per poter lavorare con gli operatori automatici e le code di chiamata. È possibile usare una licenza *gratuita Sistema telefonico Microsoft 365 - Utente* virtuale. Per ottenere queste licenze, vedere [Licenza utente virtuale.](teams-add-on-licensing/virtual-user.md)

Più avanti in questo articolo viene spiegato come assegnare la licenza a un account delle risorse.

Per ottenere la licenza Utente virtuale, nell'interfaccia di amministrazione di Microsoft 365 passare ad Abbonamenti a componenti aggiuntivi di servizi di acquisto di fatturazione e scorrere fino alla fine - verrà visualizzato Sistema telefonico - Licenza Utente  >    >   virtuale.  Seleziona **Acquista ora.** Il costo è zero, ma è comunque necessario seguire questa procedura per acquisire la licenza.

### <a name="obtain-service-numbers"></a>Ottenere numeri di servizio

I numeri di servizio sono facoltativi per gli operatori automatici e le code di chiamata, tuttavia è necessario almeno un numero di servizio per consentire ai chiamanti di raggiungere la configurazione dell'operatore automatico e della coda di chiamata. Per qualsiasi operatore automatico o coda di chiamata che desideri essere raggiungibile direttamente da un numero di servizio, devi avere un account delle risorse con un numero di servizio associato.

Gli account delle risorse possono usare numeri di servizio a numero verde o a numero verde. Puoi richiedere nuovi numeri o portarne di nuovi da un altro gestore.

Per ottenere nuovi numeri di servizio, consulta Recupero [dei numeri di telefono di servizio.](getting-service-phone-numbers.md)

Per trasferire un numero da un altro gestore, consulta [Trasferire i numeri di telefono in Teams.](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)

## <a name="create-a-resource-account"></a>Creare un account delle risorse

È possibile creare un account delle risorse nell'interfaccia di amministrazione di Teams.

![Screenshot dell'interfaccia utente aggiungi account risorsa](media/resource-account-add.png)

1. Nell'interfaccia di amministrazione di Teams espandere **Impostazioni a livello di organizzazione** e quindi fare clic su Account **risorse.**

2. Fare clic su **Aggiungi**.

3. Nel riquadro **Aggiungi account risorsa** compilare il campo Nome **visualizzato,** Nome **utente** e il tipo di **account risorsa.** Il tipo di account della risorsa può **essere** operatore automatico o coda **di** chiamata, a seconda di come intendi utilizzare questo account della risorsa.

4. Fare clic su **Salva**.

![Screenshot di un elenco di account delle risorse](media/resource-accounts-page.png)

## <a name="assign-a-license"></a>Assegnare una licenza

Per ogni account della risorsa è necessario assegnare una licenza Sistema telefonico *Microsoft 365 -* Utente virtuale o *Sistema telefonico.*

![Screenshot dell'interfaccia utente Assegna licenze nell'interfaccia di amministrazione di Microsoft 365](media/resource-account-assign-virtual-user-license.png)

1. Nell'interfaccia di amministrazione di Microsoft 365 fare clic sull'account della risorsa a cui si vuole assegnare una licenza.

2. Nella scheda **Licenze e app,** in **Licenze,** selezionare Sistema telefonico **Microsoft 365 - Utente virtuale.**

3. Fare clic **su Salva modifiche.**

## <a name="assign-a-service-number"></a>Assegnare un numero di servizio

Se si prevede di usare l'account della risorsa con un operatore automatico o una coda di chiamata che richiede un numero di servizio, assegnare un numero all'account della risorsa.

![Screenshot dell'interfaccia utente Assegna numero di servizio](media/resource-account-assign-phone-number.png)

1. Nell'interfaccia di amministrazione  di Teams, nella pagina Account risorse, selezionare l'account della risorsa a cui assegnare un numero di servizio e quindi fare clic su **Assegna/Annulla assegnazione.**

2. **Nell'elenco a** discesa Tipo di numero di telefono scegliere il tipo di numero da usare.

3. Nella casella **Numero di telefono assegnato,** cerca il numero che desideri utilizzare e fai clic su **Aggiungi.**

4. Fare clic su **Salva**.


Per assegnare un routing diretto o un numero ibrido a un account delle risorse, è necessario usare PowerShell:

`Set-CsOnlineApplicationInstance -Identity aa-contoso_main@contoso64.net -OnpremPhoneNumber +19295550150`

## <a name="next-steps"></a>Passaggi successivi

Una volta completata la configurazione dell'account della risorsa e aver assegnato un numero di servizio, se necessario, sei pronto a usare l'account della risorsa con un operatore automatico o una coda di chiamata.

Vedere i riferimenti seguenti:

 - [Operatore automatico cloud](create-a-phone-system-auto-attendant.md)

 - [Coda di chiamata cloud](create-a-phone-system-call-queue.md)

È possibile modificare il nome visualizzato e **il** tipo di account risorsa **dell'account** della risorsa usando **l'opzione Modifica.** Al **termine,** fare clic su Salva.

## <a name="change-an-existing-resource-account-to-use-a-virtual-user-license"></a>Modificare un account delle risorse esistente per usare una licenza utente virtuale

Se si decide di cambiare le licenze  dell'account delle risorse esistente da una licenza Sistema telefonico a una licenza Utente virtuale, è necessario acquisire la licenza utente virtuale gratuita e quindi seguire i passaggi dell'interfaccia di amministrazione di Microsoft 365 per spostare gli utenti in un altro [abbonamento.](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription)

> [!WARNING]
> Rimuovere sempre una licenza Sistema telefonico completa e assegnare la licenza Utente virtuale nella stessa attività di licenza. Se si rimuove la licenza precedente, salvare le modifiche all'account, aggiungere la nuova licenza e quindi salvare di nuovo le impostazioni dell'account, l'account delle risorse potrebbe non funzionare più come previsto. In questo caso, è consigliabile creare un nuovo account della risorsa per la licenza Utente virtuale e rimuovere l'account di risorsa interrotto.

## <a name="skype-for-business-server-2019"></a>Skype for Business Server 2019

Per gli account delle risorse ospitati su Skype for Business Server 2019, che possono essere utilizzati con code di chiamata cloud e operatori automatici cloud, consulta Pianificare le code di chiamata [cloud](/SkypeforBusiness/hybrid/plan-call-queue) o pianificare gli operatori automatici [cloud.](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant) Le implementazioni ibride (numeri ospitati sul routing diretto) vengono configurate usando il cmdlet [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint) in un server locale di Skype for Business Server 2019.

Gli ID applicazione da usare durante la creazione delle istanze dell'applicazione sono:

- **Operatore automatico:** ce933385-9390-45d1-9512-c8d228074e07
- **Coda di chiamata:** 11cd3e2e-fccb-42ad-ad00-878b93575e07

> [!NOTE]
> Se desideri che la coda di chiamata o l'operatore automatico sia ricercabile dagli utenti di Skype For Business Server 2019, devi creare i tuoi account delle risorse su Skype For Business Server 2019, perché gli account delle risorse online non vengono sincronizzati con Active Directory. Quando i record SRV DNS per sipfederationtls risolvono il problema  in Skype for Business Server 2019, è necessario creare account delle risorse in Skype For Business Server 2019 usando SfB Management Shell e sincronizzarli con Azure AD.

Per implementazioni ibride con Skype for Business Server:

   [Pianificare gli operatori automatici cloud](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)
  
   [Pianificare le code delle chiamate cloud](/SkypeforBusiness/hybrid/plan-call-queue)
   
   [Configurare gli account delle risorse locali](/SkypeForBusiness/hybrid/configure-onprem-ra)


## <a name="delete-a-resource-account"></a>Eliminare un account di risorsa

Assicurarsi di dissociare il numero di telefono dall'account delle risorse prima di eliminarlo, per evitare di rimanere bloccati in modalità in sospeso per il numero di servizio.

A questo punto, è possibile eliminare l'account delle risorse nell'interfaccia di amministrazione di Microsoft 365, nella scheda Utenti.

Per rimuovere l'associazione di un numero di telefono per l'instradamento diretto dall'account delle risorse, usare il cmdlet seguente:

```powershell
Set-CsOnlineApplicationInstance -Identity  <Resource Account oid> -OnpremPhoneNumber ""
```
