---
title: Aggiornare AAD Connect per includere più di una foresta
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
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: Questa appendice include i passaggi dettagliati per l'aggiornamento di AAD Connect per includere più foreste come parte del consolidamento del cloud per Teams e Skype for business.
ms.openlocfilehash: cbb4811d999601524557e7106840a66682565e5f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36185489"
---
# <a name="update-aad-connect-to-include-more-than-one-forest"></a>Aggiornare AAD Connect per includere più di una foresta

Azure AD Connect supporta la [sincronizzazione da più foreste](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect-topologies). Supporta tuttavia una sola istanza di Azure AD Connect syncing to AAD. Di conseguenza, nei casi in cui Azure AD è già installato in un'unica foresta, l'istanza esistente di AAD Connect deve essere aggiornata per la sincronizzazione dalla foresta aggiuntiva.

 - Se tutte le identità sono rappresentate una sola volta in entrambe le foreste, ovvero se non sono stati apportati contatti abilitati per la posta elettronica, è possibile rieseguire semplicemente la procedura guidata di connessione AAD, scegliere "Personalizza opzioni di sincronizzazione" e quindi nella **directory Connetti **pagina, immettere il nome della foresta aggiuntiva e creds.<br><br>
 ![Pagina Connetti le tue directory](../media/cloud-consolidation-connect-your-directories.png)
 - Tuttavia, se gli utenti possono esistere in più directory e si uniscono i dati, ad esempio se gli oggetti contatto sono presenti in una foresta corrispondente agli utenti di un'altra foresta, sarà necessario disinstallare Azure AD Connect e reinstallarlo.  Il motivo è che la condizione delle regole di join tra foreste può essere configurata solo durante la prima installazione. Questa operazione viene eseguita nella pagina seguente:<br><br>
 ![La pagina di identificazione univoca degli utenti](../media/cloud-consolidation-uniquely-identifying-your-users.png)


## <a name="see-also"></a>Vedere anche

[Consolidamento cloud per Teams e Skype for business](cloud-consolidation.md)