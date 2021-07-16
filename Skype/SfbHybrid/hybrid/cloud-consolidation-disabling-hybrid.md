---
title: Disabilitare la distribuzione ibrida per completare la migrazione Teams solo
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.prod: skype-for-business-itpro
search.appverid: MET150
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
audience: ITPro
f1.keywords:
- NOCSH
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: Questo articolo include la procedura dettagliata per disabilitare l'ambiente ibrido come parte del consolidamento del cloud per Teams e Skype for Business.
ms.openlocfilehash: 87bd1f6e0dcabed067174972dd0f0fc51149beb0
ms.sourcegitcommit: 405b22cfd94e50d651f4c3f73fb46780cd8a6d06
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/15/2021
ms.locfileid: "53453645"
---
# <a name="disable-your-hybrid-configuration-to-complete-migration-to-teams-only"></a>Disabilitare la configurazione ibrida per completare la migrazione a Teams solo 

In questo articolo viene descritto come disabilitare la configurazione ibrida prima di rimuovere le autorizzazioni dell'ambiente Skype for Business locale. Questo è il passaggio 2 della procedura seguente per rimuovere le autorizzazioni dell'ambiente locale:

- Passaggio 1. [Spostare tutti gli utenti necessari da locale a online.](decommission-move-on-prem-users.md)

- **Passaggio 2. Disabilitare la configurazione ibrida.** (Questo articolo)

- Passaggio 3. [Eseguire la migrazione degli endpoint dell'applicazione ibrida da locale a online.](decommission-move-on-prem-endpoints.md)

- Passaggio 4. [Rimuovere la distribuzione locale Skype for Business .](decommission-remove-on-prem.md)

> [!NOTE]
> I passaggi 2 e 3 devono essere evasi nella stessa finestra di manutenzione perché gli endpoint delle applicazioni ibride esistenti non saranno individuabili tra i passaggi 2 e il completamento del passaggio 3.


## <a name="summary"></a>Riepilogo

Dopo aver aggiornato tutti gli utenti da Skype for Business locale a Teams Solo in Microsoft 365, è possibile rimuovere le autorizzazioni per la distribuzione Skype for Business locale.

Prima di rimuovere le autorizzazioni per la distribuzione di Skype for Business locale e rimuovere qualsiasi hardware, è necessario separare logicamente la distribuzione locale da Microsoft 365 disabilitando la distribuzione ibrida. La disabilitazione ibrida prevede i quattro passaggi seguenti:

1. [Aggiornare i record DNS in modo che puntino Microsoft 365](#update-dns-to-point-to-microsoft-365).

2. [Modificare la modalità di coesistenza per l'organizzazione Teams solo](#change-the-coexistence-mode-for-your-organization-to-teams-only).

3. [Disabilitare lo spazio degli indirizzi SIP condiviso (noto anche come "dominio diviso") nell'Microsoft 365 organizzazione](#disable-shared-sip-address-space-in-microsoft-365-organization).

4. [Disabilitare la comunicazione tra locale e Microsoft 365](#disable-communication-between-on-premises-and-microsoft-365)

Questi passaggi separano logicamente la distribuzione locale di Skype for Business Server da Microsoft 365 e assicurati che l'organizzazione sia completamente Teams solo. Dopo aver completato questi passaggi, è possibile rimuovere le autorizzazioni della distribuzione di Skype for Business locale utilizzando uno dei due metodi a cui si fa riferimento in Decidere come gestire gli attributi dopo la rimozione delle [autorizzazioni.](cloud-consolidation-managing-attributes.md)

> [!Important] 
> Al termine di questa separazione logica, gli attributi msRTCSIP da Active Directory locale hanno ancora valori e continueranno a essere sincronizzati tramite Azure AD Connessione in Azure AD. La modalità di rimozione delle autorizzazioni per l'ambiente locale dipende dal fatto che si intenda o meno lasciare tali attributi sul posto o prima di cancellarli da Active Directory locale. Tenere presente che la cancellazione degli attributi msRTCSIP locali dopo la migrazione dall'ambiente locale potrebbe comportare la perdita del servizio per gli utenti. I dettagli e i compromessi dei due approcci di rimozione delle autorizzazioni sono descritti in Decidere come gestire gli attributi [dopo la rimozione.](cloud-consolidation-managing-attributes.md)

## <a name="update-dns-to-point-to-microsoft-365"></a>Aggiornare DNS in modo che punti a Microsoft 365

Il DNS esterno dell'organizzazione per l'organizzazione locale deve essere aggiornato in modo che i record di Skype for Business puntino a Microsoft 365 anziché alla distribuzione locale. 

Inoltre, i record CNAME per meet o dialin (se presente) possono essere eliminati. Infine, tutti i record DNS Skype for Business nella rete interna devono essere rimossi.

Per informazioni dettagliate sull'aggiornamento dei record DNS, vedere [Update DNS entries to enable your organization to be all Teams Only](decommission-manage-dns-entries.md).

## <a name="change-the-coexistence-mode-for-your-organization-to-teams-only"></a>Modificare la modalità di coesistenza per l'organizzazione Teams solo

Questo passaggio garantisce che qualsiasi nuovo utente dell'organizzazione sia sempre creato come Teams solo utente. 

Se si tenta di modificare la modalità tenant in Teams Solo verrà verificata automaticamente l'esistenza di eventuali record DNS locali che potrebbero essere stati persi nel passaggio 1 e identificheranno tali record nell'output. La modifica della modalità tenant in Teams avrà esito positivo solo dopo l'aggiornamento di tutti i record DNS per l'organizzazione. 

Per modificare la modalità tenant in Teams eseguire solo il comando seguente da una Teams di PowerShell.

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Global
```

In alternativa, è possibile utilizzare l'interfaccia di amministrazione di Teams per modificare la modalità di coesistenza del tenant in TeamsOnly, in "Impostazioni a livello di organizzazione" -> "Teams aggiornamento".    

## <a name="disable-shared-sip-address-space-in-microsoft-365-organization"></a>Disabilitare lo spazio di indirizzi SIP condiviso nell Microsoft 365 interno
    
Per disabilitare lo spazio di indirizzi SIP condiviso, eseguire il comando seguente da una finestra Teams PowerShell.

```PowerShell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false
```
 
## <a name="disable-communication-between-on-premises-and-microsoft-365"></a>Disabilitare la comunicazione tra locale e Microsoft 365

Per disabilitare la comunicazione tra l'ambiente locale e Microsoft 365, eseguire il comando seguente da una finestra di PowerShell locale:

```PowerShell
Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false
```


## <a name="see-also"></a>Vedere anche

- [Consolidamento cloud per Teams e Skype for Business](cloud-consolidation.md)

- [Rimuovi le autorizzazioni dell'ambiente locale Skype for Business](decommission-on-prem-overview.md)

