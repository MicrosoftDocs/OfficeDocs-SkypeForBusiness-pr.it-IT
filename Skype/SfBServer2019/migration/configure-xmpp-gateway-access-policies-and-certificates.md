---
title: Configurare criteri di accesso e certificati del gateway XMPP
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'La Federazione XMPP definisce una distribuzione esterna basata sul protocollo XMPP (eXtensible Messaging and Presence Protocol). Una configurazione XMPP consente agli utenti di accedere agli utenti del dominio XMPP:'
ms.openlocfilehash: c5231016729cd40619bbcfe48ebfcf59eff9182a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187334"
---
# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a>Configurare criteri di accesso e certificati del gateway XMPP

La Federazione XMPP definisce una distribuzione esterna basata sul protocollo XMPP (eXtensible Messaging and Presence Protocol). Una configurazione XMPP consente agli utenti di accedere agli utenti del dominio XMPP:
  
- Messaggistica istantanea e presenza-persona a persona
    
- Creazione di contatti federati XMPP nel client Skype for business
    
Quando si configurano i criteri per il supporto di partner federati XMPP, i criteri si applicano agli utenti di domini federati XMPP, ma non agli utenti di provider di servizi messaggistica istantanea SIP (Session Initiation Protocol) o di domini federati SIP. Si configura un partner federato XMPP per ogni dominio federato XMPP in cui si vuole consentire agli utenti di aggiungere contatti e comunicare. Dopo aver inserito i criteri, è necessario configurare i certificati del gateway XMPP. 
  
> [!NOTE]
> La funzionalità XMPP è deprecata in Skype for Business Server 2019, ma può essere proseguita in un server legacy in coesistenza con Skype for Business Server 2019. Assicurarsi di avere già distribuito il gateway XMPP (Skype for Business Server 2015/Lync Server 2013) e configurare i criteri di accesso per consentire agli utenti il gateway XMPP legacy. Per informazioni dettagliate, vedere [migrazione della Federazione XMPP](migrating-xmpp-federation.md). 
  
### <a name="configure-an-external-access-policy-to-enable-users-for-legacy-xmpp-gateway"></a>Configurare un criterio di accesso esterno per consentire agli utenti il gateway XMPP legacy

1. Aprire il pannello di controllo di Skype for Business Server legacy.
    
2. Nella barra di spostamento sinistra fare clic su **Federazione e accesso esterno**, quindi fare clic su **criteri di accesso esterno**.
    
3. Fare clic su **Nuovo** e quindi su **Criteri utente**.
    
4. Immettere un nome per il criterio utente di accesso esterno.
    
5. Specificare una descrizione per i criteri degli utenti di Access esterni.
    
6. Selezionare **Abilita comunicazioni con gli utenti federati**.
    
7. Selezionare **Abilita comunicazioni con utenti federati XMPP**.
    
8. Fare clic su **conferma** per salvare le modifiche apportate ai criteri per il sito o per gli utenti. 
    

