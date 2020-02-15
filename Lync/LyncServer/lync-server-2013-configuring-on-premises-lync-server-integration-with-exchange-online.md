---
title: Configurazione dell'integrazione di Lync Server locale con Exchange Online
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring on-premises Lync Server integration with Exchange Online
ms:assetid: 95a20117-2064-43c4-94fe-cac892cadb6f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh533880(v=OCS.15)
ms:contentKeyID: 48184900
ms.date: 03/30/2018
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ca82ae3078a2fd158e48f0dcd5906e3ae6d6983d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030499"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-on-premises-lync-server-2013-integration-with-exchange-online"></a>Configurazione dell'integrazione di Lync Server 2013 locale con Exchange Online

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2018-03-30_

I clienti che utilizzano le distribuzioni di Lync Server 2013 locali possono configurare l'interoperabilità con Microsoft Outlook Web App in Microsoft Exchange online in una modalità di distribuzione ibrida. Le caratteristiche di interoperabilità includono accesso Single Sign-on e messaggistica immediata (IM) e integrazione della presenza con l'interfaccia di Outlook Web App. Per abilitare questa integrazione, è necessario configurare il server perimetrale nella distribuzione di Lync Server locale completando le attività seguenti:

  - Configurare uno spazio di indirizzi SIP condiviso

  - Configurare un provider di hosting nel server perimetrale

  - Verificare la replica dell'archivio di gestione centrale aggiornato

Se Lync Server 2013 è integrato con Exchange Online, un utente che sta tentando di accedere a messaggistica istantanea da OWA è considerato un utente remoto o esterno. In questo scenario, l'utente deve disporre di un criterio di accesso esterno assegnato con l'opzione seguente selezionata:

**Abilita comunicazioni con utenti remoti**

Abilitare questa opzione se si desidera che gli utenti dell'organizzazione che si trovano all'esterno del firewall, ad esempio i telelavoratori e gli utenti che viaggiano, siano in grado di connettersi a Lync Server tramite Internet.

Per ulteriori informazioni, vedere [gestire i criteri di accesso esterno in Lync Server 2013](lync-server-2013-manage-external-access-policy-for-your-organization.md).

<div>

## <a name="configure-a-shared-sip-address-space"></a>Configurare uno spazio di indirizzi SIP condiviso

Per integrare Lync Server 2013 locale con Exchange Online, è necessario configurare uno spazio di indirizzi SIP condiviso. Lo stesso spazio di indirizzi di dominio SIP è supportato sia da Lync Server che dal servizio Exchange Online.

Utilizzando Lync Server Management Shell, configurare il server perimetrale per la federazione eseguendo il cmdlet **Set-CsAccessEdgeConfiguration** , utilizzando i parametri visualizzati nell'esempio seguente:

    Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

  - **AllowFederatedUsers** specifica se agli utenti interni è consentito comunicare con utenti di domini federati. Questa proprietà determina inoltre se gli utenti interni possono comunicare con gli utenti in uno scenario di spazio degli indirizzi SIP condiviso con Lync Server e Exchange Online.

Per informazioni dettagliate sull'utilizzo di Lync Server Management Shell, vedere [Lync server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).

</div>

<div>

## <a name="configure-a-hosting-provider-on-the-edge-server"></a>Configurare un provider di hosting nel server perimetrale

Utilizzare Lync Server Management Shell per configurare un provider di hosting nel server perimetrale. A tale scopo, eseguire il cmdlet **New-CsHostingProvider** , utilizzando i parametri nell'esempio seguente:

    New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification

<div>


> [!NOTE]
> Se si utilizza Office 365 gestito da 21Vianet in Cina, sostituire il valore per il parametro <STRONG>ProxyFqdn</STRONG> in questo esempio ("exap.um.Outlook.com") con il nome di dominio completo per il servizio gestito da 21ViaNet: "exap.um.partner.Outlook.cn".



</div>

  - **Identity** specifica un identificatore di valore stringa univoco per il provider di hosting da creare (ad esempio, "Exchange Online"). I valori che contengono spazi devono essere racchiusi tra virgolette doppie.

  - **Enabled** indica se la connessione di rete tra il dominio dell'organizzazione e il provider di hosting è abilitata. Questa impostazione deve essere impostata su **true**.

  - **EnabledSharedAddressSpace** consente di indicare se il provider di hosting verrà utilizzato in uno scenario con spazio di indirizzamento SIP condiviso. Questa impostazione deve essere impostata su **true**.

  - **HostsOCSUsers** indica se il provider di hosting viene utilizzato per ospitare Office Communications Server o Lync Server. Questo valore deve essere impostato su **false**.

  - **ProxyFQDN** specifica il nome di dominio completo (FQDN) del server proxy utilizzato dal provider di hosting. Per Exchange Online, il nome di dominio completo è exap.um.outlook.com.

  - La **lingua locale** indica se il server proxy utilizzato dal provider di hosting è contenuto nella topologia di Lync Server. Questo valore deve essere impostato su **false**.

  - **VerificationLevel** indica il livello di verifica consentito per i messaggi inviati e ricevuti dal provider ospitato. Specificare **UseSourceVerification**. Questa opzione si basa sul livello di verifica incluso nei messaggi inviati dal provider di hosting. Se questo livello non viene specificato, il messaggio verrà rifiutato come non verificabile.

</div>

<div>

## <a name="verify-replication-of-the-updated-central-management-store"></a>Verificare la replica dell'archivio di gestione centrale aggiornato

Le modifiche apportate utilizzando i cmdlet nelle sezioni precedenti vengono applicate automaticamente al server perimetrale e generalmente richiedono meno di un minuto per la replica. È possibile verificare lo stato della replica e che le modifiche sono state applicate al server perimetrale utilizzando i cmdlet seguenti.

Per verificare gli aggiornamenti della replica su un server interno nella distribuzione di Lync Server, eseguire il cmdlet seguente:

    Get-CsManagementStoreReplicationStatus

Per verificare che le modifiche siano state applicate, eseguire il cmdlet seguente nel server perimetrale:

    Get-CsHostingProvider -LocalStore

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Fornire ai messaggi vocali di Lync Server 2013 utenti la messaggistica unificata di Exchange ospitata](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md)  
[Integrazione della messaggistica unificata di Exchange ospitata in Lync Server 2013](lync-server-2013-hosted-exchange-unified-messaging-integration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

