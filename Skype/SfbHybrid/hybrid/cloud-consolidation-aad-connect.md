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
f1.keywords:
- NOCSH
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: Questa appendice include la procedura dettagliata per aggiornare AAD Connect per includere più foreste come parte del consolidamento del cloud per Teams e Skype for Business.
ms.openlocfilehash: a61a45c8a492afd761f8cc6b1020b591851645b8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049098"
---
# <a name="update-aad-connect-to-include-more-than-one-forest"></a>Aggiornare AAD Connect per includere più di una foresta

Azure AD Connect supporta la [sincronizzazione da più foreste.](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-topologies) Tuttavia, supporta una sola istanza di Azure AD Connect che esegue la sincronizzazione con AAD. Pertanto, nei casi in cui Azure AD è già installato in una foresta, l'istanza esistente di AAD Connect deve essere aggiornata per la sincronizzazione dalla foresta aggiuntiva.

 - Se tutte le identità sono rappresentate una sola volta in entrambe le foreste (ovvero non sono stati effettuati contatti abilitati alla posta elettronica),  è sufficiente eseguire di nuovo la procedura guidata AAD Connect, scegliere "Personalizza opzioni di sincronizzazione" e quindi nella pagina Connetti directory immettere il nome della foresta e delle identità aggiuntive.<br><br>
 ![Pagina Connetti le directory](../media/cloud-consolidation-connect-your-directories.png)
 - Tuttavia, se gli utenti possono esistere in più directory e si uniranno i dati (ad esempio, se gli oggetti contatto esistono in una foresta corrispondente agli utenti di un'altra foresta), sarà necessario disinstallare Azure AD Connect e reinstallarlo.  Questo perché la condizione delle regole di join tra foreste può essere configurata solo durante la prima installazione. Questa operazione viene eseguita nella pagina seguente:<br><br>
 ![Pagina Identificazione univoca degli utenti](../media/cloud-consolidation-uniquely-identifying-your-users.png)


## <a name="see-also"></a>Vedere anche

[Consolidamento del cloud per Teams e Skype for Business](cloud-consolidation.md)