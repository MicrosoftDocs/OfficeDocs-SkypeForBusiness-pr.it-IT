---
title: Update AAD Connect per includere più di una foresta
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
description: In questa appendice sono riportati i passaggi dettagliati per l'aggiornamento di AAD Connect per includere più foreste nell'ambito del consolidamento del cloud per i team e per Skype for business.
ms.openlocfilehash: 3d3d72c14957f0ed8932d95fcd2dbe9ec9c1e37e
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41696061"
---
# <a name="update-aad-connect-to-include-more-than-one-forest"></a>Update AAD Connect per includere più di una foresta

Azure AD Connect supporta la [sincronizzazione da più foreste](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect-topologies). Tuttavia, supporta solo un'istanza di Azure AD Connect syncing to AAD. Pertanto, nei casi in cui Azure AD è già installato in una foresta, è necessario aggiornare l'istanza esistente di AAD Connect per eseguire la sincronizzazione dalla foresta aggiuntiva.

 - Se tutte le identità sono rappresentate solo una volta in entrambe le foreste (ovvero se non sono stati apportati contatti abilitati alla posta elettronica), è possibile rieseguire la procedura guidata per la connessione di AAD, scegliere "Personalizza opzioni di sincronizzazione" e quindi nella pagina **Connetti le directory** immettere il nome della foresta aggiuntiva e creds.<br><br>
 ![Pagina Connetti le directory](../media/cloud-consolidation-connect-your-directories.png)
 - Tuttavia, se gli utenti possono esistere in più di una directory e si intende unire i dati (ad esempio, se gli oggetti contatto sono presenti in una foresta corrispondente agli utenti di un'altra foresta), sarà necessario disinstallare Azure AD Connect e reinstallarlo.  Ciò è dovuto al fatto che la condizione per le regole di join tra foreste può essere configurata solo durante la prima installazione. Questa operazione viene fatta nella pagina seguente:<br><br>
 ![La pagina di identificazione univoca degli utenti](../media/cloud-consolidation-uniquely-identifying-your-users.png)


## <a name="see-also"></a>Vedere anche

[Consolidamento cloud per Teams e Skype for business](cloud-consolidation.md)