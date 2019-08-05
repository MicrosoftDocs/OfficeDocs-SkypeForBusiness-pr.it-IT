---
title: Configurazione del supporto federativo per un cliente Skype for business online
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
localization_priority: Normal
description: "Se si distribuisce Skype for business nell'organizzazione, è possibile eseguire la Federazione con i domini di uno o più clienti Skype for business online. "
ms.openlocfilehash: c6cf36abbbf8876a8aa349d4576b45220517b89e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188792"
---
# <a name="configuring-federation-support-for-a-skype-for-business-online-customer-in-skype-for-business-server"></a>Configurazione del supporto federativo per un cliente Skype for business online in Skype for Business Server 

È possibile specificare i servizi di comunicazione per gli utenti dell'organizzazione in uno dei modi seguenti:

  - La distribuzione di Skype for Business Server nell'organizzazione (noti come *Servizi locali*) e la configurazione degli account utente di Skype for business nell'organizzazione.
  - Configurare un account del cliente di Microsoft Skype for business online con un provider di hosting e configurare gli account utente con il provider di hosting (noto come *servizi online*).

Se si distribuisce Skype for business nell'organizzazione, è possibile eseguire la Federazione con i domini di uno o più clienti Skype for business online. Per consentire la Federazione tra gli utenti della distribuzione Skype for business locale e gli utenti di un cliente Skype for business online, è necessario configurare il supporto per il dominio e gli utenti del cliente Skype for business online.

> [!NOTE]  
> Questa documentazione descrive solo le procedure per la configurazione dell'organizzazione in modo da supportare la Federazione con un cliente Skype for business online. Questa documentazione non descrive le procedure per la configurazione del cliente Skype for business online per il supporto della Federazione. 

## <a name="prerequisites-for-federating-with-a-skype-for-business-online-customer"></a>Prerequisiti per la Federazione con un cliente Skype for business online

Per eseguire la Federazione con un cliente di Skype for business online, è necessario avere già completato la distribuzione e la configurazione iniziale di Skype for Business Server nell'organizzazione. Sono inclusi i seguenti:

  - Distribuzione di almeno un server Standard Edition o un pool Front-end Enterprise Edition nell'organizzazione. 
  - Abilitazione degli account utente interni per Skype for Business Server. 
  - Distribuzione di almeno un server perimetrale e gli altri componenti necessari per supportare l'accesso degli utenti esterni. Per informazioni dettagliate, vedere [gestione della Federazione e accesso esterno a Skype for Business Server](../managing-federation-and-external-access.md).
  - Abilitazione del supporto federativo all'interno dell'organizzazione e configurazione del metodo appropriato per il controllo dell'accesso da parte di domini federati. Per informazioni dettagliate, vedere [abilitare o disabilitare l'accesso remoto agli utenti](../access-edge/enable-or-disable-remote-user-access.md) e [gestire i provider federati SIP per l'organizzazione](../sip-providers/manage-sip-federated-providers-for-your-organization.md).
  - Abilitazione dell'accesso utente esterno per gli utenti dell'organizzazione. Per informazioni dettagliate, vedere [assegnare criteri di accesso degli utenti esterni a un utente abilitato per Skype for business](../external-access-policies/assign-an-external-user-access-policy.md).



## <a name="configure-federation-support-for-a-skype-for-business-online-domain"></a>Configurare il supporto federativo per un dominio Skype for business online

Per la Federazione con un cliente Skype for business online è necessario eseguire la procedura seguente:

  - Configurare il supporto per il dominio del cliente di Skype for business online 2010 (ad esempio, contoso.onmicrosoft.com). Come specificato in [prerequisiti per la Federazione con un cliente Skype for business online](#prerequisites-for-federating-with-a-skype-for-business-online-customer), è necessario avere già abilitato la Federazione per l'organizzazione. L'abilitazione della Federazione richiede l'impostazione del metodo da usare per controllare l'accesso da domini federati. Se l'organizzazione è stata configurata per l'uso dell'individuazione, l'aggiunta del dominio all'elenco consentiti dell'organizzazione è facoltativa. Se non è stata abilitata l'individuazione del dominio, è necessario aggiungere il nome di dominio del cliente Skype for business online all'elenco dei domini consentiti. È possibile aggiungere un nome di dominio usando il pannello di controllo di Skype for Business Server oppure eseguendo il cmdlet **New-CsAllowedDomain** . Per informazioni dettagliate sull'uso del pannello di controllo di Skype for Business Server, incluso l'abilitazione dell'individuazione dei domini, vedere [gestire i provider federati SIP per l'organizzazione in Skype for Business Server](../sip-providers/manage-sip-federated-providers-for-your-organization.md). Per informazioni dettagliate sull'uso del cmdlet **New-CsAllowedDomain** per aggiungere un dominio, vedere [New-CsAllowedDomain](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsAllowedDomain).

    > [!NOTE]  
    > Un cliente di Skype for business online può avere più domini. Se si vuole eseguire la Federazione con più di uno dei domini, è necessario configurare il supporto per ogni singolo dominio con cui si vuole supportarla e l'amministratore del cliente Skype for business online deve abilitare la Federazione per ognuno dei domini essere federati.

  - Configurare il supporto per il provider di hosting del dominio del cliente Skype for business online con cui si vuole eseguire la Federazione. Usare la procedura descritta in questa sezione per configurare il supporto per il provider di hosting.

    > [!NOTE]  
    > Questo passaggio è obbligatorio solo per la Federazione con un dominio di un cliente Skype for business online, non per la Federazione con qualsiasi dominio distribuito localmente nella posizione di un partner federato.


### <a name="to-configure-support-for-a-hosting-provider"></a>Per configurare il supporto per un provider di hosting

1.  Da un server front-end avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for Business Server**e quindi su **Skype for Business Server Management Shell**.

2.  Eseguire il cmdlet **New-CsHostingProvider** per creare e configurare il provider di hosting. Ad esempio, eseguire:
    
        New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification -Enabled $True -EnabledSharedAddressSpace $False -HostsOCSUsers $False -IsLocal $False
    
    Nell'esempio precedente vengono impostati i parametri seguenti:
    
      - **Identity** specifica un identificatore di valore stringa univoco per il provider di hosting da creare. Si noti che il comando non riesce se è già stato configurato un provider esistente per questo valore Identity.
    
      - **ProxyFqdn** specifica il nome di dominio completo (FQDN) per il server proxy usato dal provider di hosting. Questo valore non può essere modificato. Se il provider di hosting cambia server proxy è necessario eliminare e ricreare la voce per il provider.
    
      - **VerificationLevel** specifica come vengono verificati i messaggi di posta elettronica inviati da un provider di hosting per verificare che siano stati inviati da tale provider.
    
      - **Enabled ** indica se la connessione di rete tra il dominio dell'organizzazione e il provider di hosting è abilitata. Finché il valore non verrà impostato su **True **, le due organizzazioni non potranno scambiarsi messaggi.
    
      - **EnabledSharedAddressSpace ** indica se il provider di hosting verrà utilizzato in uno scenario con spazio degli indirizzi SIP condiviso (dominio diviso).
    
      - **HostsOCSUsers** indica se il provider di hosting viene usato per ospitare gli account di Skype for Business Server. Se **False **, il provider ospiterà altri tipi di account, ad esempio quelli di Microsoft Exchange.
    
      - La **lingua locale** indica se il server proxy usato dal provider di hosting è contenuto nella topologia di Skype for Business Server.
    
    Per informazioni dettagliate sull'uso di questo cmdlet, vedere [New-CsHostingProvider](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsHostingProvider).

## <a name="configure-user-access-for-federation-with-a-skype-for-business-online-customer"></a>Configurare l'accesso degli utenti per la Federazione con un cliente Skype for business online 

È necessario configurare gli account utente di tutti gli utenti dell'organizzazione per consentire loro di comunicare con partner federati. Questa configurazione viene applicata per tutti i partner federati, inclusi i domini dei clienti di Microsoft Skype for business online con cui si supporta la Federazione. Per informazioni dettagliate sulla configurazione del supporto federativo per gli account utente, vedere [configurare i criteri per controllare l'accesso degli utenti federati](../external-access-policies/configure-policies-to-control-federated-user-access.md) e [assegnare un criterio di accesso degli utenti esterni a un utente abilitato per Skype for business](../external-access-policies/assign-an-external-user-access-policy.md).

## <a name="verify-communications-with-a-skype-for-business-online-customer-in-skype-for-business-server"></a>Verificare le comunicazioni con un cliente Skype for business online in Skype for Business Server

Per consentire agli utenti di Skype for business nell'organizzazione di comunicare con gli utenti di un cliente Skype for business online, è necessario che siano stati completati i passaggi seguenti:

  - Sono stati soddisfatti tutti i prerequisiti. Questo include la distribuzione di server interni e Edge, l'abilitazione del supporto federativo per l'organizzazione e la configurazione degli account utente. Per informazioni dettagliate, Vedi [prerequisiti per la Federazione con un cliente Skype for business online](#prerequisites-for-federating-with-a-skype-for-business-online-customer).
  - Supporto configurato per l'accesso ai domini nella distribuzione interna. Questo include la creazione di una voce del provider host e la configurazione della distribuzione per consentire l'accesso dal dominio del cliente Skype for business online. Per informazioni dettagliate, vedere [configurare il supporto federativo per un dominio Skype for business online](#configure-federation-support-for-a-skype-for-business-online-domain).
  - Configurato gli account utente per supportare la Federazione. Per informazioni dettagliate, vedere [configurare l'accesso degli utenti per la Federazione con un cliente Skype for business online](#configure-user-access-for-federation-with-a-skype-for-business-online-customer).

Dopo aver completato tutti questi passaggi e l'amministratore del cliente Skype for business online completa tutta la configurazione dei propri servizi online per supportare la Federazione con l'organizzazione, verificare le comunicazioni provando le comunicazioni tra un utenti interni dell'organizzazione e un utente del cliente Skype for business online. Se la comunicazione non riesce, usare lo strumento di registrazione dall'Edge Server per acquisire i file di log e Trace per risolvere il problema. 
