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
ms.openlocfilehash: 0b8c77f7d6371ba1bfefa9837488415405e48f67
ms.sourcegitcommit: a6f4c459b9c8154814a8a5b098bde1e374348c99
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/05/2022
ms.locfileid: "66615802"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a>Gestire gli account di risorsa in Microsoft Teams

[!INCLUDE [set-up-resource-account-steps](./includes/set-up-resource-account-steps.md)]

## <a name="next-steps"></a>Passaggi successivi

Dopo aver completato la configurazione dell'account delle risorse e aver assegnato un numero di servizio, se necessario, sei pronto per usare l'account della risorsa con un operatore automatico o una coda di chiamata.

Per altre informazioni, vedere i riferimenti seguenti:

- [Operatore automatico cloud](create-a-phone-system-auto-attendant.md)
- [Coda di chiamata cloud](create-a-phone-system-call-queue.md)

È possibile modificare l'account della risorsa **Nome visualizzato** e tipo di **account risorsa** usando l'opzione **Modifica** . Al termine, fare clic su **Salva** .

## <a name="change-an-existing-resource-account-to-use-a-teams-phone-resource-account-license"></a>Modificare un account di risorse esistente per usare una licenza dell'account di risorse del telefono di Teams

Se si decide di cambiare le licenze dell'account delle risorse esistente da una licenza **di Teams Phone Standard** a una licenza **account risorsa Telefono di Microsoft Teams**, sarà necessario acquisire la licenza **gratuita Account di risorse di Teams Phone** e quindi seguire i passaggi nella interfaccia di amministrazione di Microsoft 365 [spostare gli utenti in un abbonamento diverso](/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription).

> [!WARNING]
> Rimuovere sempre una licenza di Teams Phone Standard completa e assegnare la licenza **Telefono di Microsoft Teams Account risorse** nella stessa attività di licenza. Se si rimuove la licenza precedente, si salvano le modifiche dell'account, si aggiunge la nuova licenza e quindi si salvano di nuovo le impostazioni dell'account, l'account della risorsa potrebbe non funzionare più come previsto. In questo caso, è consigliabile creare un nuovo account per le risorse per la licenza **Account risorse di Telefono di Microsoft Teams** e rimuovere l'account delle risorse danneggiato.

## <a name="skype-for-business-server-2019"></a>Skype for Business Server 2019

Per gli account di risorse ospitati su Skype For Business Server 2019 che possono essere utilizzati con code di chiamata cloud e operatori automatici cloud, consulta [Pianificare code di chiamata cloud](/SkypeforBusiness/hybrid/plan-call-queue) o [Plan Cloud auto attendants](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant). Le implementazioni ibride (numeri ospitati nel routing diretto) vengono configurate utilizzando il cmdlet [New-CsHybridApplicationEndpoint](/powershell/module/skype/new-cshybridapplicationendpoint) in un server locale Skype for Business Server 2019.

Gli ID applicazione che è necessario usare durante la creazione delle istanze dell'applicazione sono:

- **Operatore automatico:** ce933385-9390-45d1-9512-c8d228074e07
- **Coda di chiamata:** 11cd3e2e-fccb-42ad-ad00-878b93575e07

> [!NOTE]
> Se desideri che la coda di chiamata o l'operatore automatico sia disponibile per la ricerca da parte degli utenti di Skype For Business Server 2019, devi creare i tuoi account di risorse su Skype For Business Server 2019, poiché gli account delle risorse online non vengono sincronizzati con Active Directory. Quando i record SRV DNS per sipfederationtls vengono risolti in Skype for Business Server 2019, gli account delle risorse **devono** essere creati in Skype For Business Server 2019 utilizzando sfB Management shell e sincronizzati con Azure AD.

Per le implementazioni ibride con Skype for Business Server:

   [Pianificare gli operatori automatici cloud](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)

   [Pianificare le code delle chiamate cloud](/SkypeforBusiness/hybrid/plan-call-queue)

   [Configurare gli account delle risorse locali](/SkypeForBusiness/hybrid/configure-onprem-ra)

## <a name="delete-a-resource-account"></a>Eliminare un account di risorsa

Assicurarsi di dissociare il numero di telefono dall'account della risorsa prima di eliminarlo, per evitare che il numero di servizio rimanga bloccato in modalità in sospeso.

Dopo aver eseguito questa operazione, è possibile eliminare l'account della risorsa nel interfaccia di amministrazione di Microsoft 365, nella scheda Utenti.

Per rimuovere l'associazione da un numero di telefono di routing diretto dall'account della risorsa, usare il cmdlet seguente:

```powershell
Remove-CsPhoneNumberAssignment -Identity <Resource Account Object ID> -PhoneNumber <assigned phone number> -PhoneNumberType DirectRouting
```
