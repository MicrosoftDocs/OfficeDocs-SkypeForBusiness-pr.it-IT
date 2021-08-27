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
ms.localizationpriority: medium
description: 'La federazione XMPP definisce una distribuzione esterna basata sul protocollo XMPP (eXtensible Messaging and Presence Protocol). Una configurazione XMPP consente agli utenti di accedere agli utenti del dominio XMPP tramite:'
ms.openlocfilehash: c442d0c4f5b5443e378be5afc031f7489860e42a
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58594306"
---
# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a>Configurare criteri e certificati di accesso al gateway XMPP

La federazione XMPP definisce una distribuzione esterna basata sul protocollo XMPP (eXtensible Messaging and Presence Protocol). Una configurazione XMPP consente agli utenti di accedere agli utenti del dominio XMPP tramite:
  
- Messaggistica istantanea e presenza - solo da persona a persona
    
- Creazione di contatti federati XMPP nel client Skype for Business client
    
Quando si configurano criteri per il supporto dei partner federati XMPP, i criteri si applicano agli utenti dei domini federati XMPP, ma non agli utenti dei provider di servizi di messaggistica istantanea SIP (Session Initiation Protocol) o dei domini federati SIP. Configurare un partner federato XMPP per ogni dominio federato XMPP con cui si desidera consentire agli utenti di aggiungere contatti e comunicare. Dopo aver configurato i criteri, è necessario configurare i certificati del gateway XMPP. 
  
> [!NOTE]
> La funzionalità XMPP è deprecata Skype for Business Server 2019, ma può essere continuata in un server legacy in coesistenza con Skype for Business Server 2019. Assicurarsi di aver già distribuito il server legacy (Skype for Business Server 2015 / Lync Server 2013) Gateway XMPP e di aver configurato i criteri di accesso per abilitare gli utenti per il gateway XMPP legacy. Per informazioni dettagliate, vedere [Migrating XMPP Federation](migrating-xmpp-federation.md). 
  
### <a name="configure-an-external-access-policy-to-enable-users-for-legacy-xmpp-gateway"></a>Configurare un criterio di accesso esterno per abilitare gli utenti per il gateway XMPP legacy

1. Apri il Pannello di controllo Skype for Business Server legacy.
    
2. Sulla barra di spostamento sinistra fare clic su **Federazione e accesso esterno** e quindi su **Criteri di accesso esterno**.
    
3. Fare clic su **Nuovo** e quindi su **Criteri utente**.
    
4. Immettere un nome per l'impostazione dei criteri utente di accesso esterno.
    
5. Specificare una descrizione per l'impostazione dei criteri utente di accesso esterno.
    
6. Selezionare **Abilita comunicazioni con utenti federati**.
    
7. Selezionare **Abilita le comunicazioni con gli utenti federati XMPP**.
    
8. Fare clic su **Commit** per salvare le modifiche apportate ai criteri utente o sito. 
    

