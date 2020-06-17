---
title: Configurare criteri e certificati di accesso al gateway XMPP
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'La federazione XMPP definisce una distribuzione esterna basata sul protocollo XMPP (eXtensible Messaging and Presence Protocol). Una configurazione XMPP consente agli utenti di accedere agli utenti di dominio XMPP:'
ms.openlocfilehash: f94cd3bc0a769165f6ffe8ecabea8b7f48a1ff07
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753936"
---
# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a>Configurare criteri e certificati di accesso al gateway XMPP

La federazione XMPP definisce una distribuzione esterna basata sul protocollo XMPP (eXtensible Messaging and Presence Protocol). Una configurazione XMPP consente agli utenti di accedere agli utenti di dominio XMPP:
  
- Messaggistica istantanea e presenza-solo persona a persona
    
- Creazione di contatti federati XMPP nel client Skype for business
    
Quando si configurano i criteri per il supporto di partner federati XMPP, i criteri vengono applicati agli utenti di domini federati XMPP, ma non agli utenti di provider di servizi di messaggistica istantanea SIP (Session Initiation Protocol) o di domini federati SIP. È possibile configurare un partner federato XMPP per ogni dominio federato XMPP che si desidera consentire agli utenti di aggiungere contatti e comunicare con. Dopo aver configurato i criteri, è necessario configurare i certificati del gateway XMPP. 
  
> [!NOTE]
> La funzionalità XMPP è obsoleta in Skype for Business Server 2019, ma può essere continuata in un server legacy in coesistenza con Skype for Business Server 2019. Assicurarsi di aver già distribuito il gateway XMPP del server legacy (Skype for Business Server 2015/Lync Server 2013) e aver configurato i criteri di accesso per abilitare gli utenti per il gateway XMPP legacy. Per informazioni dettagliate, vedere [migrazione della Federazione XMPP](migrating-xmpp-federation.md). 
  
### <a name="configure-an-external-access-policy-to-enable-users-for-legacy-xmpp-gateway"></a>Configurare un criterio di accesso esterno per abilitare gli utenti per il gateway XMPP legacy

1. Aprire il pannello di controllo di Skype for Business Server legacy.
    
2. Sulla barra di spostamento sinistra fare clic su **Federazione e accesso esterno** e quindi su **Criteri di accesso esterno**.
    
3. Fare clic su **Nuovo** e quindi su **Criteri utente**.
    
4. Immettere un nome per l'impostazione dei criteri utente di accesso esterno.
    
5. Specificare una descrizione per l'impostazione dei criteri utente di accesso esterno.
    
6. Selezionare **Abilita comunicazioni con utenti federati**.
    
7. Selezionare **Abilita le comunicazioni con gli utenti federati XMPP**.
    
8. Fare clic su **Commit** per salvare le modifiche apportate ai criteri utente o sito. 
    

