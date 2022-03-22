---
title: Procedure consigliate per l'accesso condizionale e la conformità Microsoft Teams Rooms
ms.author: czawideh
author: cazawideh
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
description: Informazioni sulle procedure consigliate per l'accesso condizionale e i criteri di conformità dei dispositivi intune e le procedure consigliate per Microsoft Teams Rooms.
ms.openlocfilehash: 1f4bec9d47b73be1638b1740afeb879b4dfb4026
ms.sourcegitcommit: dafe48cea1643e1bd79390482da9b002d7e9e0bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/16/2022
ms.locfileid: "63689142"
---
# <a name="conditional-access-and-intune-compliance-for-microsoft-teams-rooms"></a>Accesso condizionale e conformità di Intune per Microsoft Teams Rooms

Questo articolo fornisce i requisiti e le procedure consigliate per l'accesso condizionale e i criteri di conformità dei dispositivi intune per Microsoft Teams Rooms usati negli spazi condivisi.

## <a name="requirements"></a>Requisiti

Teams Rooms deve essere già distribuito nei dispositivi a cui si vogliono assegnare i criteri di accesso condizionale. Se non è ancora stata distribuita Teams Rooms, vedere Creare account delle risorse per le chat room e i dispositivi [Teams](with-office-365.md) condivisi e Distribuire Microsoft Teams Rooms in [Android](../devices/collab-bar-deploy.md) per altre informazioni.

Per usare l'accesso condizionale è necessario un piano di servizio Azure Active Directory P1. È incluso nella licenza Microsoft Teams Rooms licenza.

## <a name="teams-rooms-conditional-access-best-practices"></a>Teams Rooms procedure consigliate per l'accesso condizionale

I criteri di accesso condizionale possono proteggere il processo di accesso nei dispositivi in spazi condivisi e usati da più persone. Per una panoramica dell'accesso condizionale in Azure Active Directory (Azure AD), vedere Che cos'è [l'accesso condizionale in Azure Active Directory?](/azure/active-directory/conditional-access/overview).

Quando si usa l'accesso condizionale per proteggere Teams Rooms, prendere in considerazione le procedure consigliate seguenti:

-   Per semplificare la distribuzione e la gestione, includere Microsoft 365 account delle risorse della chat room associati Teams Rooms in un unico gruppo di utenti.

-   Avere uno standard di denominazione per tutti gli account Teams Rooms risorse. Ad esempio, i nomi di account "mtr-room1@contoso.com" e "mtr-room2@contoso.com" iniziano entrambi con il prefisso "mtr-".
    Quando i nomi degli account sono standardizzati, è possibile usare i gruppi dinamici in Azure AD per applicare automaticamente i criteri di accesso condizionale a tutti questi account contemporaneamente. Per [altre informazioni sui gruppi dinamici,](/azure/active-directory/enterprise-users/groups-dynamic-membership) vedere Regole per l'appartenenza a gruppi popolati dinamicamente.

Per un elenco delle assegnazioni di accesso condizionale supportate per Teams Rooms, vedere [Criteri di accesso condizionale supportati](supported-ca-and-compliance-policies.md#supported-conditional-access-policies).

## <a name="example-conditional-access-policy"></a>Criteri di accesso condizionale di esempio

Nell'esempio seguente i criteri di accesso condizionale funzionano come segue:

1.  L'account che accede deve essere membro di un gruppo di utenti specifico, in questo esempio il gruppo "Dispositivi condivisi".

2.  L'account che accede deve solo provare ad accedere a Exchange Online, Microsoft Teams o SharePoint Online. I tentativi di accesso a qualsiasi altra app client verranno rifiutati.

3.  L'account della risorsa deve accedere alla piattaforma Windows dispositivo.

4.  L'account della risorsa deve anche accedere da un percorso attendibile noto.

Se queste condizioni vengono soddisfatte correttamente e l'utente immette il nome utente e la password corretti, l'account della risorsa accederà Teams.

## <a name="conditional-access-with-microsoft-intune-compliance-for-teams-rooms"></a>Accesso condizionale con Microsoft Intune conformità per Teams Rooms

I requisiti di conformità sono regole definite che i dispositivi devono soddisfare per essere contrassegnati come conformi, ad esempio la versione minima del sistema operativo. I dispositivi devono essere considerati conformi prima di poter essere usati per accedere a un account delle risorse.

Per un elenco dei criteri di conformità di Intune supportati per Teams Rooms, vedere [Criteri di conformità dei dispositivi supportati](supported-ca-and-compliance-policies.md#supported-device-compliance-policies).

Per altre informazioni sulla configurazione di Intune Teams dispositivi Android, vedere Configurare Intune per registrare Teams [dispositivi basati su Android](../devices/phones-displays-deploy.md#configure-intune-to-enroll-teams-android-based-devices).

## <a name="example-windows-only-conditional-access-with-intune-device-compliance"></a>Esempio (solo Windows: Accesso condizionale con conformità dei dispositivi Intune

In questo esempio per Teams Rooms in Windows

1. Richiedere che un firewall sia in esecuzione Teams Rooms in Windows.

2. Richiedi che Microsoft Defender sia in esecuzione in Teams Rooms.

3. Se una Teams room non soddisfa uno di questi requisiti, non verrà contrassegnata come conforme e i dispositivi non effettuano l'accesso.

Questo criterio di conformità si applica a tutti gli utenti, non solo Teams account delle risorse.
