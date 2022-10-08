---
title: Creare account di risorse per sale e dispositivi teams condivisi
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
ms.custom: seo-marvel-apr2020
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: Leggere questo articolo per informazioni su come creare account di risorse per sale e dispositivi condivisi, tra cui Microsoft Teams Rooms, Teams Rooms su Surface Hub e hot desking sugli schermi di Teams.
ms.openlocfilehash: 1448496137088ce04dc087825e67f7d8b31afd80
ms.sourcegitcommit: 3ad7b46e31890fba7abe739138cd49527d5ca6b7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/05/2022
ms.locfileid: "68475498"
---
# <a name="create-and-configure-resource-accounts-for-rooms-and-shared-teams-devices"></a>Creare e configurare account di risorse per sale e dispositivi Teams condivisi

Questo articolo fornisce la procedura per creare account di risorse per gli spazi e i dispositivi condivisi e include i passaggi per configurare gli account delle risorse per Microsoft Teams Rooms in Windows, Teams Rooms su Android, Teams Rooms su Surface Hub e hot desking sugli schermi di Teams.

Gli account delle risorse di Microsoft 365 sono cassette postali e account di Teams dedicati a risorse specifiche, ad esempio una sala o un proiettore. Questi account delle risorse possono rispondere automaticamente agli inviti alle riunioni usando le regole definite al momento della creazione. Ad esempio, se si ha una risorsa comune, ad esempio una sala riunioni, è possibile configurare un account di risorsa per la sala riunioni che accetta o rifiuta automaticamente gli inviti alle riunioni in base alla disponibilità del calendario. 

Ogni account delle risorse è univoco per una singola installazione Microsoft Teams Rooms o Teams visualizza l'implementazione hot desking.

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

> [!NOTE]
> Se si usano i pannelli di Microsoft Teams, l'account della risorsa Teams Rooms accede sia a Teams Rooms che ai pannelli di Teams associati.

> [!NOTE]
> **Skype for Business** <br><br>
> Se è necessario abilitare l'uso dell'account delle risorse con Skype for Business, vedere [Distribuire Microsoft Teams Rooms con Skype for Business Server](with-skype-for-business-server-2015.md)

## <a name="before-you-begin"></a>Prima di iniziare

### <a name="requirements"></a>Requisiti

A seconda dell'ambiente, sono necessari uno o più ruoli per creare account delle risorse.

|**Ambiente**|**Ruoli obbligatori**|
|-----|-----|
|Azure Active Directory  <br/> |Amministratore globale o Amministratore utente  <br/> |
|Active Directory  <br/> |Active Directory Enterprise Admins, Domain Admins o hanno diritti delegati per la creazione di utenti. Diritti di sincronizzazione di Azure Active Directory Connect.  <br/> |
|Exchange Online  <br/> |Amministratore globale o Amministratore di Exchange   <br/> |
|Exchange Server  <br/> |Gestione organizzazione di Exchange o Gestione destinatari   <br/> |

Se si creano account delle risorse per Teams Rooms, l'UPN deve corrispondere all'indirizzo SMTP dell'account della risorsa. Prima di distribuire Teams Rooms, vedere [i requisiti](requirements.md) di Microsoft Teams Rooms.

### <a name="what-license-do-you-need"></a>Di quale licenza hai bisogno?

[!INCLUDE [mtr-device-config-license-include](../includes/mtr-device-config-license-include.md)]

## <a name="create-a-resource-account"></a>Creare un account di risorsa

[!INCLUDE [mtr-device-config-account-include](../includes/mtr-device-config-account-include.md)]

## <a name="configure-mailbox-properties"></a>Configurare le proprietà della cassetta postale

[!INCLUDE [mtr-device-config-mailbox-include](../includes/mtr-device-config-mailbox-include.md)]

## <a name="turn-off-password-expiration"></a>Disattivare la scadenza della password

[!INCLUDE [mtr-device-config-password-include](../includes/mtr-device-config-password-include.md)]

## <a name="assign-a-meeting-room-license"></a>Assegnare una licenza per una sala riunioni

[!INCLUDE [mtr-device-config-assign-include](../includes/mtr-device-config-assign-include.md)]

## <a name="next-steps"></a>Passaggi successivi

### <a name="meeting-policies"></a>Criteri riunione

[!INCLUDE [mtr-device-config-policies-include](../includes/mtr-device-config-policies-include.md)]

### <a name="calling"></a>Chiamate

Non esistono requisiti univoci per abilitare le chiamate con gli account delle risorse. È possibile abilitare l'account della risorsa per le chiamate allo stesso modo in cui si abilita un utente normale.

> [!NOTE]
> È consigliabile disattivare la segreteria telefonica per i dispositivi condivisi assegnando un criterio di chiamata agli account delle risorse del dispositivo. Per altre informazioni, vedi [Chiamate e inoltro di chiamata in Teams](../teams-calling-policy.md) .

[!INCLUDE [mtr-device-config-calendar-include](../includes/mtr-device-config-calendar-include.md)]

## <a name="related-articles"></a>Articoli correlati

[Configurare gli account per Microsoft Teams Rooms](rooms-configure-accounts.md)

[Piano per Microsoft Teams Rooms](rooms-plan.md)

[Distribuire Microsoft Teams Rooms](rooms-deploy.md)

[Gestire Microsoft Teams Rooms](rooms-manage.md).

[Licenze di Microsoft Teams Rooms](rooms-licensing.md)
