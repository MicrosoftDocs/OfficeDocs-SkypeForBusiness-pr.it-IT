---
title: Configurazione del supporto federativo per un cliente di Skype for business online
ms.reviewer: ''
ms:assetid: e5f7f38d-ede5-4af3-88c2-026e8a78df12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202193(v=OCS.15)
ms:contentKeyID: 48185669
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: "Se si distribuisce Skype for business nell'organizzazione, è possibile eseguire la Federazione con i domini di uno o più clienti Skype for business online. "
ms.openlocfilehash: b7488d21463782a978c9a3d6263d9fdfc2e59dd9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037286"
---
# <a name="configuring-federation-support-for-a-skype-for-business-online-customer-in-skype-for-business-server"></a>Configurazione del supporto federativo per un cliente di Skype for business online in Skype for Business Server 

È possibile fornire servizi di comunicazione agli utenti dell'organizzazione in uno dei modi seguenti:

  - La distribuzione di Skype for Business Server nell'organizzazione (noti come *Servizi locali*) e la configurazione degli account utente di Skype for business nell'organizzazione.
  - Configurare un account cliente di Microsoft Skype for business online con un provider di hosting e impostare gli account utente con il provider di hosting (noto come *servizi online*).

Se si distribuisce Skype for business nell'organizzazione, è possibile eseguire la Federazione con i domini di uno o più clienti Skype for business online. Per abilitare la Federazione tra gli utenti della distribuzione di Skype for business locale e gli utenti di un cliente di Skype for business online, è necessario configurare il supporto per il dominio e gli utenti del cliente Skype for business online.

> [!NOTE]  
> Questa documentazione descrive solo le procedure per la configurazione dell'organizzazione per supportare la Federazione con un cliente di Skype for business online. In questa documentazione non sono descritte le procedure per la configurazione del cliente Skype for business online per il supporto della Federazione. 

## <a name="prerequisites-for-federating-with-a-skype-for-business-online-customer"></a>Prerequisiti per la Federazione con un cliente di Skype for business online

Per la Federazione con un cliente di Skype for business online, è necessario avere già completato la distribuzione iniziale e la configurazione di Skype for Business Server nell'organizzazione. Sono incluse le attività seguenti:

  - Distribuzione di almeno un server Standard Edition o un pool Enterprise Edition front end nell'organizzazione. 
  - Abilitazione degli account utente interni per Skype for Business Server. 
  - Distribuzione di almeno un server perimetrale e gli altri componenti necessari per il supporto dell'accesso degli utenti esterni. Per informazioni dettagliate, vedere [Managing Federation and External Access to Skype for Business Server](../managing-federation-and-external-access.md).
  - Abilitazione del supporto per la federazione nell'organizzazione e configurazione del metodo appropriato per il controllo dell'accesso da parte dei domini federati. Per ulteriori informazioni, vedere [abilitare o disabilitare l'accesso degli utenti remoti](../access-edge/enable-or-disable-remote-user-access.md) e [gestire i provider federati SIP per l'organizzazione](../sip-providers/manage-sip-federated-providers-for-your-organization.md).
  - Abilitazione dell'accesso utente esterno per gli utenti dell'organizzazione. Per ulteriori informazioni, vedere [assegnare un criterio di accesso utente esterno a un utente abilitato di Skype for business](../external-access-policies/assign-an-external-user-access-policy.md).



## <a name="configure-federation-support-for-a-skype-for-business-online-domain"></a>Configurare il supporto federativo per un dominio Skype for business online

Per la Federazione con un cliente di Skype for business online, è necessario eseguire le operazioni seguenti:

  - Configurare il supporto per il dominio del cliente di Skype for business online 2010 (ad esempio, contoso.onmicrosoft.com). Come specificato nei [prerequisiti per la Federazione con un cliente di Skype for business online](#prerequisites-for-federating-with-a-skype-for-business-online-customer), è necessario avere già abilitato la Federazione per l'organizzazione. Se si abilita la federazione, è necessario specificare il metodo da utilizzare per controllare l'accesso da parte dei domini federati. Se l'organizzazione è stata configurata in modo da utilizzare l'individuazione, l'aggiunta del dominio all'elenco dei domini consentiti dell'organizzazione è facoltativa. Se non è stata abilitata l'individuazione del dominio, è necessario aggiungere il nome di dominio del cliente Skype for business online all'elenco dei domini consentiti. È possibile aggiungere un nome di dominio utilizzando il pannello di controllo di Skype for Business Server o eseguendo il cmdlet **New-CsAllowedDomain** . Per informazioni dettagliate sull'utilizzo del pannello di controllo di Skype for Business Server, inclusa l'abilitazione dell'individuazione dei domini, vedere [gestire i provider federati SIP per l'organizzazione in Skype for Business Server](../sip-providers/manage-sip-federated-providers-for-your-organization.md). Per informazioni dettagliate sull'utilizzo del cmdlet **New-CsAllowedDomain** per aggiungere un dominio, vedere [New-CsAllowedDomain](https://docs.microsoft.com/powershell/module/skype/New-CsAllowedDomain).

    > [!NOTE]  
    > Un cliente Skype for business online può disporre di più domini. Se si desidera eseguire la Federazione con più domini, è necessario configurare il supporto per ogni singolo dominio con cui si desidera supportare il servizio federativo e l'amministratore del cliente Skype for business online deve abilitare la Federazione per ognuno dei domini essere federato.

  - Configurare il supporto per il provider di hosting del dominio dei clienti di Skype for business online con cui si desidera eseguire la Federazione. Utilizzare la procedura disponibile in questa sezione per configurare il supporto per tale provider.

    > [!NOTE]  
    > Questo passaggio è necessario solo per la Federazione con un dominio di un cliente di Skype for business online, non per la Federazione con qualsiasi dominio distribuito in locale nella posizione di un partner federato.


### <a name="to-configure-support-for-a-hosting-provider"></a>Per configurare il supporto per un provider di hosting

1.  Da un front end server, avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for Business Server**e quindi su **Skype for Business Server Management Shell**.

2.  Eseguire il cmdlet **New-CsHostingProvider** per creare e configurare il provider di hosting. Ad esempio, eseguire:
    
        New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification -Enabled $True -EnabledSharedAddressSpace $False -HostsOCSUsers $False -IsLocal $False
    
    Nell'esempio precedente vengono impostati i parametri seguenti:
    
      - **Identity** specifica un identificatore di valore stringa univoco per il provider di hosting che si sta creando. Il comando avrà esito negativo se è stato già configurato un provider esistente con lo stesso valore di Identity.
    
      - **ProxyFQDN** specifica il nome di dominio completo (FQDN) del server proxy utilizzato dal provider di hosting. Questo valore non può essere modificato. Se il provider di hosting cambia server proxy, sarà necessario eliminare e quindi ricreare la voce per il provider.
    
      - **VerificationLevel** specifica come o se i messaggi inviati da un provider di hosting devono essere verificati per accertare che provengano effettivamente da quel provider.
    
      - **Enabled** indica se la connessione di rete fra il proprio dominio e il provider di hosting è abilitata. Finché il valore non viene impostato su **True**, le due organizzazioni non potranno scambiarsi messaggi.
    
      - **EnabledSharedAddressSpace** indica se il provider di hosting verrà utilizzato in uno scenario con spazio degli indirizzi SIP condiviso (dominio diviso).
    
      - **HostsOCSUsers** indica se il provider di hosting viene utilizzato per ospitare gli account di Skype for Business Server. Se **False**, il provider ospiterà altri tipi di account, ad esempio quelli di Microsoft Exchange.
    
      - La **lingua locale** indica se il server proxy utilizzato dal provider di hosting è contenuto nella topologia di Skype for Business Server.
    
    Per informazioni dettagliate sull'utilizzo di questo cmdlet, vedere [New-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/New-CsHostingProvider).

## <a name="configure-user-access-for-federation-with-a-skype-for-business-online-customer"></a>Configurare l'accesso degli utenti per la Federazione con un cliente di Skype for business online 

È necessario configurare gli account utente di tutti gli utenti nell'organizzazione per consentire loro di comunicare con i partner federati. Questa configurazione viene applicata a tutti i partner federati, inclusi i domini dei clienti di Microsoft Skype for business online con cui si supporta la Federazione. Per informazioni dettagliate sulla configurazione del supporto federativo per gli account utente, vedere [configurare i criteri per controllare l'accesso degli utenti federati](../external-access-policies/configure-policies-to-control-federated-user-access.md) e [assegnare un criterio di accesso utente esterno a un utente abilitato di Skype for business](../external-access-policies/assign-an-external-user-access-policy.md).

## <a name="verify-communications-with-a-skype-for-business-online-customer-in-skype-for-business-server"></a>Verificare le comunicazioni con un cliente di Skype for business online in Skype for Business Server

Per consentire agli utenti di Skype for business nell'organizzazione di comunicare con gli utenti di un cliente di Skype for business online, è necessario aver completato i passaggi seguenti:

  - Sono stati soddisfatti tutti i prerequisiti. Ciò include la distribuzione dei server interni e perimetrali, l'abilitazione del supporto federativo per l'organizzazione e la configurazione degli account utente. Per ulteriori informazioni, vedere [prerequisiti per la Federazione con un cliente di Skype for business online](#prerequisites-for-federating-with-a-skype-for-business-online-customer).
  - Il supporto per l'accesso al dominio è stato configurato nella distribuzione interna. Ciò include la creazione di una voce del provider host e la configurazione della distribuzione per consentire l'accesso dal dominio del cliente di Skype for business online. Per ulteriori informazioni, vedere [configurare il supporto federativo per un dominio Skype for business online](#configure-federation-support-for-a-skype-for-business-online-domain).
  - Gli account utente sono stati configurati per il supporto della federazione. Per ulteriori informazioni, vedere [configurare l'accesso utente per la Federazione con un cliente di Skype for business online](#configure-user-access-for-federation-with-a-skype-for-business-online-customer).

Dopo aver completato tutti questi passaggi e l'amministratore del cliente Skype for business online ha completato tutta la configurazione dei servizi online per supportare la Federazione con l'organizzazione, verificare le comunicazioni verificando le comunicazioni tra un utente interno dell'organizzazione e utente del cliente Skype for business online. Se la comunicazione non ha esito positivo, utilizzare lo strumento di registrazione dal server perimetrale per acquisire i file di log e di traccia per risolvere il problema. 
