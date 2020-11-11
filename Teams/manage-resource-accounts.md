---
title: Gestire gli account delle risorse in teams
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
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.orgwidesettings.resourceaccounts.overview
- seo-marvel-apr2020
description: In questo articolo verrà illustrato come creare, modificare e gestire gli account delle risorse in Microsoft teams.
ms.openlocfilehash: 7ccc7a26c83357d68147381101ef8a97184f03f4
ms.sourcegitcommit: 247b2587a60b1609947310ec82d51f47cf829703
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/11/2020
ms.locfileid: "48993518"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a>Gestire gli account di risorsa in Microsoft Teams

Un account di risorse è un oggetto utente disabilitato in Azure AD e può essere usato per rappresentare le risorse in generale. Ad esempio, un account di risorse può essere usato in Exchange per rappresentare sale riunioni e consentire loro di avere un numero di telefono e un calendario. Un account delle risorse può essere ospitato in Microsoft 365 o in locale con Skype for Business Server 2019.

In Microsoft teams è necessario un account di risorse per ogni operatore automatico o coda di chiamata. Gli account delle risorse possono anche essere assegnati numeri di telefono di servizio. Ecco come assegnare i numeri di telefono agli operatori automatici e alle code di chiamata che consentono ai chiamanti provenienti da team esterni di raggiungere l'operatore automatico o la coda di chiamata.

Questo articolo illustra come creare gli account delle risorse e prepararli per l'uso con gli operatori automatici e le code di chiamata.

Prima di iniziare le procedure descritte in questo articolo, verificare di aver eseguito le operazioni seguenti:

- [Ottenere licenze utente virtuali](#obtain-virtual-user-licenses)
- [Ottenere i numeri di servizio](#obtain-service-numbers)

### <a name="obtain-virtual-user-licenses"></a>Ottenere licenze utente virtuali

Ogni account delle risorse richiede una licenza per l'utilizzo con gli operatori automatici e le code di chiamata. È possibile usare un *sistema telefonico gratuito Microsoft 365-* licenza per gli utenti virtuali. Per ottenere queste licenze, vedere [licenza per gli utenti virtuali](teams-add-on-licensing/virtual-user.md).

Viene illustrato come assegnare la licenza a un account delle risorse più avanti in questo articolo.

Per ottenere la licenza per gli utenti virtuali, nell'interfaccia di amministrazione di Microsoft 365 **Billing** passare a  >  **Purchase services**  >  **abbonamenti al componente aggiuntivo** fatturazione servizi di acquisto e scorrere fino alla fine: si vedrà il *sistema telefonico-licenza utente virtuale* . Selezionare **Acquista ora**. È disponibile un costo zero, ma è comunque necessario seguire questa procedura per acquisire la licenza.

### <a name="obtain-service-numbers"></a>Ottenere i numeri di servizio

I numeri di servizio sono facoltativi per gli operatori automatici e le code di chiamata, tuttavia sarà necessario almeno un numero di servizio per consentire ai chiamanti di raggiungere l'operatore automatico e la configurazione delle code di chiamata. Per qualsiasi operatore automatico o coda di chiamata che si vuole raggiungere direttamente da un numero di servizio, è necessario disporre di un account delle risorse con un numero di servizio associato.

Gli account delle risorse possono usare numeri di servizio a pagamento o a numero verde. È possibile richiedere nuovi numeri o trasferire numeri esistenti da un altro vettore.

Per ottenere nuovi numeri di servizio, vedere [recupero di numeri di telefono del servizio](getting-service-phone-numbers.md).

Per convertire un numero da un altro vettore, vedere [trasferire i numeri di telefono in teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).

## <a name="create-a-resource-account"></a>Creare un account di risorse

È possibile creare un account risorse nell'interfaccia di amministrazione di teams.

![Screenshot dell'interfaccia utente Aggiungi account risorse](media/resource-account-add.png)

1. Nell'interfaccia di amministrazione di teams espandere **impostazioni a livello di organizzazione** e quindi fare clic su **account risorse**.

2. Fare clic su **Aggiungi**.

3. Nel riquadro **Aggiungi account risorse** compilare **nome visualizzato** , **nomeutente** e **tipo di account risorse**. Il tipo di account delle risorse può essere l' **operatore automatico** o la **coda di chiamata** , a seconda di come si intende usare questo account di risorse.

4. Fare clic su **Salva**.

![Screenshot di un elenco di account delle risorse](media/resource-accounts-page.png)

## <a name="assign-a-license"></a>Assegnare una licenza

Per ogni account delle risorse, è necessario assegnare un *sistema telefonico Microsoft 365-* licenza per l'utente virtuale o per il *sistema telefonico* .

![Screenshot dell'interfaccia utente di assegnazione licenze nell'area di amministrazione di Microsoft 365](media/resource-account-assign-virtual-user-license.png)

1. Nell'interfaccia di amministrazione di Microsoft 365 fare clic sull'account delle risorse a cui si vuole assegnare una licenza.

2. Nella scheda **licenze e app** , in **licenze** , selezionare **Microsoft 365 Phone System-Virtual User**.

3. Fare clic su **Salva modifiche**.

## <a name="assign-a-service-number"></a>Assegnare un numero di servizio

Se si prevede di usare l'account risorse con un operatore automatico o una coda di chiamata che richiede un numero di servizio, assegnare un numero all'account della risorsa.

![Screenshot dell'interfaccia utente assegna numero di servizio](media/resource-account-assign-phone-number.png)

1. Nell'interfaccia di amministrazione di teams, nella pagina **account risorse** , selezionare l'account delle risorse a cui si vuole assegnare un numero di servizio e quindi fare clic su **assegna/Annulla assegnazione**.

2. Nell'elenco a discesa **tipo di numero di telefono** scegliere il tipo di numero che si vuole usare.

3. Nella casella **numero di telefono assegnato** cercare il numero che si vuole usare e fare clic su **Aggiungi**.

4. Fare clic su **Salva**.


Per assegnare un routing diretto o un numero ibrido a un account di risorse, è necessario usare PowerShell:

`Set-CsOnlineApplicationInstance -Identity aa-contoso_main@contoso64.net -OnpremPhoneNumber +19295550150`

## <a name="next-steps"></a>Passaggi successivi

Dopo aver completato la configurazione dell'account delle risorse e aver assegnato un numero di servizio, se necessario, è possibile usare l'account delle risorse con un operatore automatico o una coda di chiamata.

Vedere i riferimenti seguenti:

 - [Operatore automatico cloud](create-a-phone-system-auto-attendant.md)

 - [Coda di chiamata cloud](create-a-phone-system-call-queue.md)

È possibile modificare il **nome visualizzato** dell'account delle risorse e il tipo di **account delle risorse** usando l'opzione **modifica** . Al termine, fare clic su **Salva** .

## <a name="change-an-existing-resource-account-to-use-a-virtual-user-license"></a>Cambiare un account di risorse esistente per usare una licenza utente virtuale

Se si decide di cambiare le licenze per l'account delle risorse esistenti da una licenza di **sistema telefonico** a una licenza per gli utenti virtuali, è necessario acquisire la licenza per gli utenti virtuali gratuita e quindi seguire i passaggi dell'interfaccia di amministrazione di Microsoft 365 per [spostare gli utenti in un altro abbonamento](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription).

> [!WARNING]
> Rimuovere sempre una licenza per il sistema telefonico completo e assegnare la licenza utente virtuale nella stessa attività di licenza. Se si rimuove la vecchia licenza, si salvano le modifiche dell'account, si aggiunge la nuova licenza e quindi si salvano di nuovo le impostazioni dell'account, l'account delle risorse potrebbe non funzionare più come previsto. In questo caso, è consigliabile creare un nuovo account risorse per la licenza per gli utenti virtuali e rimuovere l'account delle risorse interrotte.

## <a name="skype-for-business-server-2019"></a>Skype for Business Server 2019

Per gli account delle risorse ospitati in Skype for Business Server 2019 che possono essere usati con le code delle chiamate cloud e gli operatori automatici del cloud, vedere [pianificare le code delle chiamate cloud](/SkypeforBusiness/hybrid/plan-call-queue) o gli [operatori automatici di piano cloud](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant). Le implementazioni ibride (numeri assegnati al routing diretto) vengono configurate usando il cmdlet [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint) in un server di Skype for Business Server 2019 locale.

Gli ID applicazione che è necessario usare durante la creazione delle istanze dell'applicazione sono i seguenti:

- **Operatore automatico:** ce933385-9390-45d1-9512-c8d228074e07
- **Coda di chiamata:** 11cd3e2e-FCCB-42AD-Ad00-878b93575e07

> [!NOTE]
> Se si vuole che la coda di chiamata o l'operatore automatico siano ricercabili dagli utenti di Skype for Business Server 2019, è consigliabile creare gli account delle risorse in Skype for Business Server 2019, poiché gli account delle risorse online non vengono sincronizzati in Active Directory. Quando i record SRV DNS per sipfederationtls si risolvono in Skype for Business Server 2019, gli account delle risorse **devono** essere creati in Skype for business server 2019 usando SFB Management Shell e sincronizzati con Azure ad.

Per le implementazioni ibride con Skype for Business Server:

   [Pianificare gli operatori automatici cloud](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)
  
   [Pianificare le code delle chiamate cloud](/SkypeforBusiness/hybrid/plan-call-queue)
   
   [Configurare gli account delle risorse on-Prem](/SkypeForBusiness/hybrid/configure-onprem-ra)


## <a name="delete-a-resource-account"></a>Eliminare un account delle risorse

Assicurarsi di dissociare il numero di telefono dall'account delle risorse prima di eliminarlo, per evitare che il numero di servizio venga bloccato in modalità in sospeso.

Dopo aver eseguito questa operazione, è possibile eliminare l'account delle risorse nell'interfaccia di amministrazione di Microsoft 365, nella scheda utenti.

Per dissociare un numero di telefono di routing diretto dall'account delle risorse, usare il cmdlet seguente:

```powershell
Set-CsOnlineApplicationInstance -Identity  <Resource Account oid> -OnpremPhoneNumber ""
```
