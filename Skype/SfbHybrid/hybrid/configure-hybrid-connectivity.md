---
title: Configurare la connettività ibrida | Distribuire Skype for Business Server 2019 connect
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Istruzioni per l'implementazione della connettività ibrida tra Skype for Business Server e Teams.
ms.openlocfilehash: fee7587c641f2fd55cd8b4ac4da72b3944b819a1
ms.sourcegitcommit: 64b9f7297d33a883506893fb68d1ad5202b4df1a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/24/2021
ms.locfileid: "59682811"
---
# <a name="configure-hybrid-connectivity-between-skype-for-business-server-and-teams"></a>Configurare la connettività ibrida tra Skype for Business Server e Teams

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

**Riepilogo:** Leggere questo argomento per informazioni su come configurare la connettività ibrida tra Skype for Business Server e Teams.  La connettività ibrida consente di spostare gli utenti locali in Teams e consente agli utenti di sfruttare i servizi cloud.
  
Prima di eseguire i passaggi descritti in questo argomento, è necessario leggere [Plan hybrid connectivity between Skype for Business Server and Teams](plan-hybrid-connectivity.md).
  
Nella tabella seguente sono elencate le attività necessarie per configurare la Skype for Business ibrida e vengono forniti collegamenti agli articoli associati per ulteriori informazioni.
  
|Passaggio|Descrizione|
|:-----|:-----|
|Creare un account tenant per Microsoft 365.   <br/> |Per informazioni Microsoft 365, [vedere Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=254980).  <br/> Per verificare che l'ambiente sia pronto per Microsoft 365, vedere Requisiti [di sistema](https://products.office.com/office-system-requirements).  <br/> Per informazioni dettagliate sulla configurazione Microsoft 365, vedere [Introduzione a Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=254982).  <br/> |
|Aggiungere il dominio all'organizzazione Microsoft 365 e verificare la proprietà.  <br/> | È necessario aggiungere il dominio all'organizzazione Microsoft 365 e quindi seguire la procedura per convalidare il dominio con Microsoft 365. Questa convalida consente di verificare di essere il proprietario del dominio. <br/> Per aggiungere il dominio all'organizzazione Microsoft 365, seguire la procedura descritta in [Aggiungere un dominio a Microsoft 365](https://support.office.com/article/add-a-domain-to-office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611?ui=en-US&rs=en-US&ad=US). Leggere le linee guida seguenti relative alle implicazioni DNS per [le organizzazioni che diventano ibride.](#dns-implications-for-on-premises-organizations-that-become-hybrid) <br/> |
|Configurare la sincronizzazione di Active Directory.  <br/> |La sincronizzazione di Active Directory garantisce che Active Directory locale sia costantemente sincronizzato con Microsoft 365 in modo da creare versioni sincronizzate di ogni account utente e gruppo.  <br/> <br> **Importante:** È necessario sincronizzare gli account di Active Directory per tutti gli utenti Skype for Business dell'organizzazione tra le distribuzioni locali e online, anche se gli utenti non vengono spostati in Teams. Se non si sincronizzano tutti gli utenti, le comunicazioni tra utenti locali e online nell'organizzazione potrebbero non funzionare come previsto. Per ulteriori informazioni, vedere [Configure Azure AD Connessione for hybrid environments](configure-azure-ad-connect.md).         |
| Configurare Skype for Business ibrido. | Questa procedura prevede tre passaggi di base: <br><br> 1. Configurare l'ambiente locale per la federazione con Microsoft 365. <br> 2. Configurare l'ambiente locale in modo che ritieni attendibile Microsoft 365 e abilitare lo spazio di indirizzi SIP condiviso con Microsoft 365.<br> 3. Abilitare lo spazio di indirizzi SIP condiviso nell'Microsoft 365 organizzazione. <br><br> Inoltre, se si dispone Exchange locale, è possibile configurare OAuth tra gli ambienti Exchange locali e online. <br> <br>Per ulteriori informazioni, vedere [Configure Skype for Business hybrid](configure-federation-with-skype-for-business-online.md).
|Spostare gli utenti del programma pilota.  <br/> |Dopo aver completato i passaggi per preparare e configurare l'ambiente per Teams, è possibile iniziare a spostare gli utenti pilota nell'organizzazione Microsoft 365 online. Per ulteriori informazioni, vedere [Move users from on premises to Teams](move-users-from-on-premises-to-Teams.md).  <br/> |


## <a name="dns-implications-for-on-premises-organizations-that-become-hybrid"></a>Implicazioni DNS per le organizzazioni locali che diventano ibride

Per impostazione predefinita, i tenant vengono creati in modalità TeamsOnly. Gli amministratori non possono modificare questa configurazione. Tuttavia, le organizzazioni ibride non devono essere in modalità TeamsOnly perché ciò interromperebbe la federazione per gli utenti locali. Teams dispone di un meccanismo incorporato per garantire che la configurazione TeamsOnly a livello di tenant non venga applicata per i nuovi tenant ibridi e che la configurazione teamsOnly a livello di tenant venga rimossa dai tenant esistenti che diventano *ibridi.* Questo meccanismo si basa sul valore del record DNS LyncDiscover per qualsiasi dominio Microsoft 365 verificato (perché nella maggior parte dei casi una distribuzione locale di Skype for Business Server avrà tale record), come descritto di seguito.

Quando una nuova sottoscrizione Microsoft 365 viene elaborata per la prima volta, si verifica quanto segue:
- Se non sono ancora presenti domini Microsoft 365, il tenant viene creato in modalità TeamsOnly. Il valore viene impostato tramite TeamsUpgradeOverridePolicy, che può essere impostato solo da Microsoft. Se il valore del criterio è UpgradeToTeams, ha la precedenza su qualsiasi valore di TeamsUpgradePolicy.
- Se sono presenti domini Microsoft 365 verificati, ma non sono stati rilevati record Dns LyncDiscover pubblici o se tutti i record LyncDiscover rilevati puntano a Microsoft 365 (sipfed.online.lync.com, sipfed.online.gov.skypeforbusiness.us e così via), il tenant viene creato come modalità TeamsOnly (tramite TeamsUpgradeOverridePolicy).
- Se è presente almeno un dominio Microsoft 365 verificato per il quale viene rilevato un record LyncDiscover e tale record punta a un punto diverso da Microsoft 365, il tenant viene creato in modalità Isole.

Quando un tenant Microsoft 365 esistente viene eseguito di nuovo il provisioning (in genere a causa di una modifica nei domini verificati o nei dettagli della sottoscrizione), si verifica quanto segue:
- Se viene trovato un record LyncDiscover per uno o più domini verificati di Microsoft 365 e tale record non punta a Microsoft 365, la modalità TeamsOnly a livello di tenant (tramite TeamsUpgradeOverridePolicy) viene rimossa. La modalità tenant verrà ripristinata a qualsiasi valore specificato a livello di tenant per TeamsUpgradePolicy, che, per impostazione predefinita, è la modalità Isole.


Esistono alcune limitazioni per questo meccanismo di rilevamento automatico:
- Se l'organizzazione non dispone di record DNS pubblici, la modalità TeamsOnly non verrà rimossa poiché Microsoft 365 non sarà in grado di rilevare i record. Se l'organizzazione dispone di Skype for Business Server locale senza voci DNS pubbliche, è necessario contattare il supporto Tecnico Microsoft per eseguire il downgrade del tenant.
- Se si aggiunge/aggiorna un record DNS  pubblico a un dominio che è già un dominio verificato Microsoft 365, questa modifica DNS non viene rilevata e la modalità TeamsOnly non viene rimossa. La modalità TeamsOnly viene rimossa solo se viene eseguito di nuovo il provisioning del tenant, cosa che in genere si verifica quando viene apportata una modifica Microsoft 365 domini verificati o alla sottoscrizione.  
