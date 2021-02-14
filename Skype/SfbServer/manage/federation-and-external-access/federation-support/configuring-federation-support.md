---
title: Configurazione del supporto della federazione per un cliente Skype for Business Online
ms.reviewer: ''
ms:assetid: e5f7f38d-ede5-4af3-88c2-026e8a78df12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202193(v=OCS.15)
ms:contentKeyID: 48185669
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: "Se si distribuisce Skype for Business nell'organizzazione, è possibile attuare la federazione con i domini di uno o più clienti di Skype for Business online. "
ms.openlocfilehash: f09e717af9e5209a0bb4bfdeb0ea50abbdaf7f86
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817236"
---
# <a name="configuring-federation-support-for-a-skype-for-business-online-customer-in-skype-for-business-server"></a>Configurazione del supporto della federazione per un cliente Skype for Business online in Skype for Business Server 

È possibile fornire servizi di comunicazione agli utenti dell'organizzazione in uno dei modi seguenti:

  - Distribuzione di Skype for Business Server nell'organizzazione (noti come servizi *locali)* e configurazione degli account utente di Skype for Business nell'organizzazione.
  - Configurazione di un account cliente microsoft Skype for Business online con un provider di hosting e configurazione degli account utente con il provider di hosting (noto come *servizi online).*

Se si distribuisce Skype for Business nell'organizzazione, è possibile attuare la federazione con i domini di uno o più clienti di Skype for Business online. Per abilitare la federazione tra gli utenti della distribuzione di Skype for Business locale e gli utenti di un cliente Skype for Business online, è necessario configurare il supporto per il dominio e gli utenti del cliente skype for Business online.

> [!NOTE]  
> Questa documentazione descrive solo le procedure per configurare l'organizzazione per supportare la federazione con un cliente Skype for Business online. In questa documentazione non vengono descritte le procedure per configurare il cliente di Skype for Business online per supportare la federazione. 

## <a name="prerequisites-for-federating-with-a-skype-for-business-online-customer"></a>Prerequisiti per la federazione con un cliente di Skype for Business online

Per attuare la federazione con un cliente Skype for Business online, dovresti aver già completato la distribuzione iniziale e la configurazione di Skype for Business Server nella tua organizzazione. Sono incluse le attività seguenti:

  - Distribuzione di almeno un server Standard Edition o di un pool Enterprise Edition Front End nell'organizzazione. 
  - Abilitazione degli account utente interni per Skype for Business Server. 
  - Distribuzione di almeno un server perimetrale e degli altri componenti necessari per supportare l'accesso degli utenti esterni. Per informazioni dettagliate, vedere [Gestione della federazione e dell'accesso esterno a Skype for Business Server.](../managing-federation-and-external-access.md)
  - Abilitazione del supporto per la federazione nell'organizzazione e configurazione del metodo appropriato per il controllo dell'accesso da parte dei domini federati. Per informazioni dettagliate, vedere [Enable or disable remote user access](../access-edge/enable-or-disable-remote-user-access.md) and Manage SIP [federated providers for your organization.](../sip-providers/manage-sip-federated-providers-for-your-organization.md)
  - Abilitazione dell'accesso utente esterno per gli utenti dell'organizzazione. Per informazioni dettagliate, vedere Assegnare un criterio di accesso utente [esterno a un utente abilitato a Skype for Business.](../external-access-policies/assign-an-external-user-access-policy.md)



## <a name="configure-federation-support-for-a-skype-for-business-online-domain"></a>Configurare il supporto della federazione per un dominio di Skype for Business online

La federazione con un cliente Skype for Business online richiede di completare i passaggi seguenti:

  - Configurare il supporto per il dominio del cliente Skype for Business online 2010 (ad esempio, contoso.onmicrosoft.com). Come specificato in Prerequisiti per la federazione con un cliente [Skype for Business online,](#prerequisites-for-federating-with-a-skype-for-business-online-customer)è necessario aver già abilitato la federazione per l'organizzazione. Se si abilita la federazione, è necessario specificare il metodo da utilizzare per controllare l'accesso da parte dei domini federati. Se l'organizzazione è stata configurata in modo da utilizzare l'individuazione, l'aggiunta del dominio all'elenco dei domini consentiti dell'organizzazione è facoltativa. Se l'individuazione dei domini non è stata abilitata, è necessario aggiungere il nome di dominio del cliente Skype for Business online all'elenco dei domini consentiti. È possibile aggiungere un nome di dominio utilizzando il Pannello di controllo di Skype for Business Server o eseguendo il cmdlet **New-CSAllowedDomain.** Per informazioni dettagliate sull'uso del Pannello di controllo di Skype for Business Server, inclusa l'abilitazione dell'individuazione dei domini, vedere Gestire i provider federati SIP per l'organizzazione [in Skype for Business Server.](../sip-providers/manage-sip-federated-providers-for-your-organization.md) Per informazioni dettagliate **sull'utilizzo del cmdlet New-CSAllowedDomain** per aggiungere un dominio, vedere [New-CsAllowedDomain.](https://docs.microsoft.com/powershell/module/skype/New-CsAllowedDomain)

    > [!NOTE]  
    > Un cliente Skype for Business online può avere più domini. Se si desidera attuare la federazione con più domini, è necessario configurare il supporto per ogni singolo dominio con cui si desidera supportare la federazione e l'amministratore del cliente di Skype for Business online deve abilitare la federazione per ognuno dei domini da attuare.

  - Configurare il supporto per il provider di hosting del dominio del cliente skype for Business online con cui si desidera attuare la federazione. Utilizzare la procedura disponibile in questa sezione per configurare il supporto per tale provider.

    > [!NOTE]  
    > Questo passaggio è necessario solo per la federazione con un dominio di un cliente Skype for Business online, non per la federazione con un dominio distribuito in locale nella posizione di un partner federato.


### <a name="to-configure-support-for-a-hosting-provider"></a>Per configurare il supporto per un provider di hosting

1.  Da un Front End Server avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business Server** e quindi Skype for Business Server Management **Shell.**

2.  Eseguire il cmdlet **New-CsHostingProvider** per creare e configurare il provider di hosting. Ad esempio, eseguire:
    
        New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification -Enabled $True -EnabledSharedAddressSpace $False -HostsOCSUsers $False -IsLocal $False
    
    Nell'esempio precedente vengono impostati i parametri seguenti:
    
      - **Identity** specifica un identificatore di valore stringa univoco per il provider di hosting che si sta creando. Il comando avrà esito negativo se è stato già configurato un provider esistente con lo stesso valore di Identity.
    
      - **ProxyFQDN** specifica il nome di dominio completo (FQDN) del server proxy utilizzato dal provider di hosting. Questo valore non può essere modificato. Se il provider di hosting cambia server proxy, sarà necessario eliminare e quindi ricreare la voce per il provider.
    
      - **VerificationLevel** specifica come o se i messaggi inviati da un provider di hosting devono essere verificati per accertare che provengano effettivamente da quel provider.
    
      - **Enabled** indica se la connessione di rete fra il proprio dominio e il provider di hosting è abilitata. Finché il valore non viene impostato su **True**, le due organizzazioni non potranno scambiarsi messaggi.
    
      - **EnabledSharedAddressSpace** indica se il provider di hosting verrà utilizzato in uno scenario con spazio degli indirizzi SIP condiviso (dominio diviso).
    
      - **HostsOCSUsers** indica se il provider di hosting viene utilizzato per ospitare gli account di Skype for Business Server. Se **False**, il provider ospiterà altri tipi di account, ad esempio quelli di Microsoft Exchange.
    
      - **IsLocal** indica se il server proxy utilizzato dal provider di hosting è contenuto nella topologia di Skype for Business Server.
    
    Per informazioni dettagliate sull'utilizzo di questo cmdlet, [vedere New-CsHostingProvider.](https://docs.microsoft.com/powershell/module/skype/New-CsHostingProvider)

## <a name="configure-user-access-for-federation-with-a-skype-for-business-online-customer"></a>Configurare l'accesso utente per la federazione con un cliente di Skype for Business online 

È necessario configurare gli account utente di tutti gli utenti nell'organizzazione per consentire loro di comunicare con i partner federati. Questa configurazione viene applicata a tutti i partner federati, inclusi i domini dei clienti di Microsoft Skype for Business online con cui si supporta la federazione. Per informazioni dettagliate sulla configurazione del supporto della federazione per gli account utente, vedere Configure [policies to control federated user access](../external-access-policies/configure-policies-to-control-federated-user-access.md) and Assign an external user access policy to a Skype for Business enabled [user.](../external-access-policies/assign-an-external-user-access-policy.md)

## <a name="verify-communications-with-a-skype-for-business-online-customer-in-skype-for-business-server"></a>Verificare le comunicazioni con un cliente skype for business online in Skype for Business Server

Per consentire agli utenti di Skype for Business nell'organizzazione di comunicare con gli utenti di un cliente Skype for Business online, è necessario aver completato i passaggi seguenti:

  - Sono stati soddisfatti tutti i prerequisiti. Ciò include la distribuzione dei server perimetrali e interni, l'abilitazione del supporto della federazione per l'organizzazione e la configurazione degli account utente. Per informazioni dettagliate, vedere [Prerequisiti per la federazione con un cliente skype for Business online.](#prerequisites-for-federating-with-a-skype-for-business-online-customer)
  - Il supporto per l'accesso al dominio è stato configurato nella distribuzione interna. Ciò include la creazione di una voce del provider host e la configurazione della distribuzione per consentire l'accesso dal dominio del cliente di Skype for Business online. Per informazioni dettagliate, vedere [Configurare il supporto della federazione per un dominio di Skype for Business online.](#configure-federation-support-for-a-skype-for-business-online-domain)
  - Gli account utente sono stati configurati per il supporto della federazione. Per informazioni dettagliate, vedere [Configurare l'accesso utente per la federazione con un cliente Skype for Business online.](#configure-user-access-for-federation-with-a-skype-for-business-online-customer)

Dopo aver completato tutti questi passaggi e l'amministratore del cliente di Skype for Business online completa tutta la configurazione dei servizi online per supportare la federazione con l'organizzazione, verificare le comunicazioni testando le comunicazioni tra un utente interno dell'organizzazione e un utente del cliente Skype for Business online. Se la comunicazione non riesce, utilizzare lo strumento di registrazione dal server perimetrale per acquisire i file di registro e di traccia per risolvere il problema. 
