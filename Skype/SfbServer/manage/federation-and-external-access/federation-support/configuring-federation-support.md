---
title: Configurazione del supporto della federazione per un cliente Skype for Business Online
ms.reviewer: ''
ms:assetid: e5f7f38d-ede5-4af3-88c2-026e8a78df12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202193(v=OCS.15)
ms:contentKeyID: 48185669
mtps_version: v=OCS.15
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: "Se si distribuiscono Skype for Business nell'organizzazione, è possibile eseguire la federazione con i domini di uno o più Skype for Business clienti online. "
ms.openlocfilehash: 7d41073aadae59c6b01c7eeeb1c5072a6ca21e24
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60747142"
---
# <a name="configuring-federation-support-for-a-skype-for-business-online-customer-in-skype-for-business-server"></a>Configurazione del supporto della federazione per un cliente Skype for Business online in Skype for Business Server

È possibile fornire servizi di comunicazione agli utenti dell'organizzazione in uno dei modi seguenti:

- Distribuzione di Skype for Business Server nell'organizzazione (noti come servizi *locali)* e configurazione Skype for Business account utente nell'organizzazione.
- Configurare un account cliente di Microsoft Skype for Business Online con un provider di hosting e configurare gli account utente con il provider di hosting (noto come *servizi online).*

Se si distribuiscono Skype for Business nell'organizzazione, è possibile eseguire la federazione con i domini di uno o più Skype for Business clienti online. Per abilitare la federazione tra gli utenti della distribuzione di Skype for Business locale e gli utenti di un cliente di Skype for Business Online, è necessario configurare il supporto per il dominio e gli utenti del cliente di Skype for Business Online.

[!INCLUDE [sfbo-retirement-skype](../../../../Hub/includes/sfbo-retirement.md)]

> [!NOTE]  
> In questa documentazione vengono descritte solo le procedure per configurare l'organizzazione per supportare la federazione con un cliente Skype for Business online. In questa documentazione non vengono descritte le procedure per configurare il cliente Skype for Business Online per supportare la federazione.

## <a name="prerequisites-for-federating-with-a-skype-for-business-online-customer"></a>Prerequisiti per la federazione con un cliente Skype for Business online

Per eseguire la federazione con un Skype for Business online, è necessario aver già completato la distribuzione iniziale e la configurazione Skype for Business Server nell'organizzazione. Sono incluse le attività seguenti:

- Distribuzione di almeno un edizione Standard server o edizione Enterprise pool Front End nell'organizzazione.
- Abilitazione di account utente interni per Skype for Business Server.
- Distribuzione di almeno un server perimetrale e degli altri componenti necessari per supportare l'accesso degli utenti esterni. Per informazioni dettagliate, vedere [Managing federation and external access to Skype for Business Server](../managing-federation-and-external-access.md).
- Abilitazione del supporto per la federazione nell'organizzazione e configurazione del metodo appropriato per il controllo dell'accesso da parte dei domini federati. Per informazioni dettagliate, vedere [Enable or disable remote user access](../access-edge/enable-or-disable-remote-user-access.md) e Manage SIP [federated providers for your organization](../sip-providers/manage-sip-federated-providers-for-your-organization.md).
- Abilitazione dell'accesso utente esterno per gli utenti dell'organizzazione. Per informazioni dettagliate, vedere [Assign an external user access policy to a Skype for Business enabled user](../external-access-policies/assign-an-external-user-access-policy.md).

## <a name="configure-federation-support-for-a-skype-for-business-online-domain"></a>Configurare il supporto della federazione per un dominio Skype for Business Online

La federazione con un Skype for Business online richiede che tu completi i passaggi seguenti:

- Configurare il supporto per il dominio del cliente Skype for Business Online 2010 (ad esempio, contoso.onmicrosoft.com). Come specificato in [Prerequisites for federating with a Skype for Business Online customer,](#prerequisites-for-federating-with-a-skype-for-business-online-customer)è necessario aver già abilitato la federazione per l'organizzazione. Se si abilita la federazione, è necessario specificare il metodo da utilizzare per controllare l'accesso da parte dei domini federati. Se l'organizzazione è stata configurata in modo da utilizzare l'individuazione, l'aggiunta del dominio all'elenco dei domini consentiti dell'organizzazione è facoltativa. Se l'individuazione dei domini non è stata abilitata, è necessario aggiungere il nome di dominio del cliente Skype for Business Online all'elenco dei domini consentiti. È possibile aggiungere un nome di dominio utilizzando Skype for Business Server pannello di controllo o eseguendo il cmdlet **New-CSAllowedDomain.** Per informazioni dettagliate sull'Skype for Business Server di controllo, inclusa l'abilitazione dell'individuazione dei domini, vedere [Manage SIP federated providers for your organization in Skype for Business Server](../sip-providers/manage-sip-federated-providers-for-your-organization.md). Per informazioni dettagliate **sull'utilizzo del cmdlet New-CSAllowedDomain** per aggiungere un dominio, vedere [New-CsAllowedDomain](/powershell/module/skype/New-CsAllowedDomain).

  > [!NOTE]  
  > Un Skype for Business online può avere più domini. Se si desidera eseguire la federazione con più di uno dei domini, è necessario configurare il supporto per ogni singolo dominio con cui si desidera supportare la federazione e l'amministratore del cliente di Skype for Business Online deve abilitare la federazione per ognuno dei domini da federatire.

- Configurare il supporto per il provider di hosting del dominio Skype for Business online con cui si desidera eseguire la federazione. Utilizzare la procedura disponibile in questa sezione per configurare il supporto per tale provider.

  > [!NOTE]  
  > Questo passaggio è necessario solo per la federazione con un dominio di un cliente di Skype for Business Online, non per la federazione con un dominio distribuito in locale nella posizione di un partner federato.

### <a name="to-configure-support-for-a-hosting-provider"></a>Per configurare il supporto per un provider di hosting

1. Da un Front End Server, avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** Skype for Business Server **e** quindi fare clic su Skype for Business Server **Management Shell.**

2. Eseguire il cmdlet **New-CsHostingProvider** per creare e configurare il provider di hosting. Ad esempio, eseguire quanto segue:

    ```powershell
    New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification -Enabled $True -EnabledSharedAddressSpace $False -HostsOCSUsers $False -IsLocal $False
    ```

    Nell'esempio precedente vengono impostati i parametri seguenti:

    - **Identity** specifica un identificatore di valore stringa univoco per il provider di hosting che si sta creando. Il comando avrà esito negativo se è stato già configurato un provider esistente con lo stesso valore di Identity.

    - **ProxyFQDN** specifica il nome di dominio completo (FQDN) del server proxy utilizzato dal provider di hosting. Questo valore non può essere modificato. Se il provider di hosting cambia server proxy, sarà necessario eliminare e quindi ricreare la voce per il provider.

    - **VerificationLevel** specifica come o se i messaggi inviati da un provider di hosting devono essere verificati per accertare che provengano effettivamente da quel provider.

    - **Enabled** indica se la connessione di rete fra il proprio dominio e il provider di hosting è abilitata. Finché il valore non viene impostato su **True**, le due organizzazioni non potranno scambiarsi messaggi.

    - **EnabledSharedAddressSpace** indica se il provider di hosting verrà utilizzato in uno scenario con spazio degli indirizzi SIP condiviso (dominio diviso).

    - **HostsOCSUsers** indica se il provider di hosting viene utilizzato per ospitare Skype for Business Server account. Se **False**, il provider ospiterà altri tipi di account, ad esempio quelli di Microsoft Exchange.

    - **IsLocal** indica se il server proxy utilizzato dal provider di hosting è contenuto nella topologia Skype for Business Server locale.

    Per informazioni dettagliate sull'utilizzo di questo cmdlet, [vedere New-CsHostingProvider](/powershell/module/skype/New-CsHostingProvider).

## <a name="configure-user-access-for-federation-with-a-skype-for-business-online-customer"></a>Configurare l'accesso utente per la federazione con un Skype for Business online

È necessario configurare gli account utente di tutti gli utenti nell'organizzazione per consentire loro di comunicare con i partner federati. Questa configurazione viene applicata a tutti i partner federati, inclusi i domini dei clienti di Microsoft Skype for Business Online con cui si supporta la federazione. Per informazioni dettagliate sulla configurazione del supporto della federazione per gli account utente, vedere [Configure policies to control federated user access](../external-access-policies/configure-policies-to-control-federated-user-access.md) e Assign an external user access policy to a Skype for Business enabled [user](../external-access-policies/assign-an-external-user-access-policy.md).

## <a name="verify-communications-with-a-skype-for-business-online-customer-in-skype-for-business-server"></a>Verificare le comunicazioni con un Skype for Business online in Skype for Business Server

Per consentire Skype for Business utenti dell'organizzazione a comunicare con gli utenti di un cliente di Skype for Business Online, è necessario aver completato i passaggi seguenti:

- Sono soddisfatti tutti i prerequisiti. Ciò include la distribuzione dei server perimetrali e interni, l'abilitazione del supporto della federazione per l'organizzazione e la configurazione degli account utente. Per informazioni dettagliate, vedere [Prerequisites for federating with a Skype for Business Online customer](#prerequisites-for-federating-with-a-skype-for-business-online-customer).
- Il supporto per l'accesso al dominio è stato configurato nella distribuzione interna. Ciò include la creazione di una voce del provider host e la configurazione della distribuzione per consentire l'accesso Skype for Business dominio del cliente di Skype for Business online. Per informazioni dettagliate, vedere [Configure federation support for a Skype for Business Online domain](#configure-federation-support-for-a-skype-for-business-online-domain).
- Gli account utente sono stati configurati per il supporto della federazione. Per informazioni dettagliate, vedere [Configure user access for federation with a Skype for Business Online customer](#configure-user-access-for-federation-with-a-skype-for-business-online-customer).

Dopo aver completato tutti questi passaggi e l'amministratore del cliente di Skype for Business Online completa tutta la configurazione dei propri servizi online per supportare la federazione con l'organizzazione, verificare le comunicazioni testando le comunicazioni tra un utente interno dell'organizzazione e un utente del cliente di Skype for Business Online. Se la comunicazione non riesce, utilizzare lo strumento di registrazione dal server perimetrale per acquisire i file di registro e di traccia per risolvere il problema.
