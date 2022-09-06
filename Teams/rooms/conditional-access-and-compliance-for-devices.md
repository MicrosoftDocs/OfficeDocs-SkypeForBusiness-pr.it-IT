---
title: Procedure consigliate per l'accesso condizionale e la conformità per Microsoft Teams Rooms
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
description: Informazioni sui criteri consigliati di accesso condizionale e Intune conformità dei dispositivi e sulle procedure consigliate per Microsoft Teams Rooms.
ms.openlocfilehash: e16513a840dadf7a5cabe961a0fbbd9135da9b89
ms.sourcegitcommit: 75dfc3cd9b59282d68e35e4d7185da572eb3795c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2022
ms.locfileid: "67606545"
---
# <a name="conditional-access-and-intune-compliance-for-microsoft-teams-rooms"></a>Accesso condizionale e conformità Intune per Microsoft Teams Rooms

Questo articolo fornisce i requisiti e le procedure consigliate per l'accesso condizionale e Intune criteri di conformità dei dispositivi per Microsoft Teams Rooms usati negli spazi condivisi.

[!INCLUDE [teams-pro-license-requirement](../includes/teams-pro-license-requirement.md)]

## <a name="requirements"></a>Requisiti

Teams Rooms deve essere già distribuita nei dispositivi a cui si vogliono assegnare criteri di accesso condizionale. Se non è ancora stato distribuito Teams Rooms, vedere [Creare account di risorse per sale e dispositivi Teams condivisi](with-office-365.md) e [Distribuire Microsoft Teams Rooms su Android](../devices/collab-bar-deploy.md) per altre informazioni.

Per usare l'accesso condizionale è necessario un piano di servizio Azure Active Directory P1. È incluso nella licenza di Microsoft Teams Rooms.

## <a name="teams-rooms-conditional-access-best-practices"></a>procedure consigliate per l'accesso condizionale Teams Rooms

I criteri di accesso condizionale possono proteggere il processo di accesso nei dispositivi che si trovano in spazi condivisi e usati da più persone. Per una panoramica dell'accesso condizionale in Azure Active Directory (Azure AD), vedere [Che cos'è l'accesso condizionale in Azure Active Directory?](/azure/active-directory/conditional-access/overview).

Quando si usa l'accesso condizionale per proteggere Teams Rooms, prendere in considerazione le procedure consigliate seguenti:

-   Per semplificare la distribuzione e la gestione, includere tutti gli account di Risorse sala di Microsoft 365 associati a Teams Rooms in un unico gruppo di utenti.

-   Disporre di uno standard di denominazione per tutti gli account delle risorse Teams Rooms. Ad esempio, i nomi di account 'mtr-room1@contoso.com' e 'mtr-room2@contoso.com' iniziano entrambi con il prefisso 'mtr-'.
    Quando i nomi degli account sono standardizzati, è possibile usare i gruppi dinamici in Azure AD per applicare automaticamente i criteri di accesso condizionale a tutti questi account contemporaneamente. Per altre informazioni sui gruppi dinamici, vedere [Regole per l'appartenenza ai gruppi popolata in modo dinamico](/azure/active-directory/enterprise-users/groups-dynamic-membership) .

Per un elenco delle assegnazioni di accesso condizionale supportate per Teams Rooms, vedere Criteri di [accesso condizionale supportati](supported-ca-and-compliance-policies.md#supported-conditional-access-policies).

## <a name="example-conditional-access-policy"></a>Esempio di criteri di accesso condizionale

Nell'esempio seguente i criteri di accesso condizionale funzionano come segue:

1.  L'account che esegue l'accesso deve essere membro di un gruppo di utenti specifico, in questo esempio il gruppo "Dispositivi condivisi".

2.  L'account che accede deve provare ad accedere solo a Exchange Online, Microsoft Teams o SharePoint Online. I tentativi di accesso a qualsiasi altra app client verranno rifiutati.

3.  L'account della risorsa deve eseguire l'accesso nella piattaforma di dispositivi Windows.

4.  L'account della risorsa deve effettuare l'accesso anche da un percorso attendibile noto.

Se queste condizioni vengono soddisfatte correttamente e l'utente immette il nome utente e la password corretti, l'account della risorsa accederà a Teams.

## <a name="conditional-access-with-microsoft-intune-compliance-for-teams-rooms"></a>Accesso condizionale con conformità Microsoft Intune per Teams Rooms

I requisiti di conformità sono regole definite che i dispositivi devono soddisfare per essere contrassegnate come conformi, ad esempio la versione minima del sistema operativo. I dispositivi devono essere considerati conformi prima di poter essere usati per accedere a un account delle risorse.

Per un elenco dei criteri di conformità Intune supportati per Teams Rooms, vedere [Criteri di conformità dei dispositivi supportati](supported-ca-and-compliance-policies.md#supported-device-compliance-policies).

Per altre informazioni sulla configurazione di Intune con i dispositivi Android di Teams, vedere [Configurare Intune per registrare i dispositivi basati su Android di Teams](../devices/phones-displays-deploy.md#configure-intune-to-enroll-teams-android-based-devices).

## <a name="example-windows-only-conditional-access-with-intune-device-compliance"></a>Esempio (solo Windows): Accesso condizionale con Intune conformità del dispositivo

In questo esempio per Teams Rooms in Windows

1. Richiedi l'esecuzione di un firewall su Teams Rooms in Windows.

2. Richiedi che Microsoft Defender sia in esecuzione su Teams Rooms.

3. Se una chat room di Teams non soddisfa questi requisiti, non verrà contrassegnata come conforme e i dispositivi non accederanno.

Questo criterio di conformità si applica a tutti gli utenti, non solo agli account delle risorse di Teams.
