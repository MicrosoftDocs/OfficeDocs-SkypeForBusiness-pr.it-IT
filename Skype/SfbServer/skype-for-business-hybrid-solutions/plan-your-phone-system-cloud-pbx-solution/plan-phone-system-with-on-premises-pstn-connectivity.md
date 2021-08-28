---
title: Pianificare Sistema telefonico con connettività PSTN locale in Skype for Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/26/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 021a4c0b-d5de-4155-a506-650d758624aa
description: Informazioni sulle considerazioni sulla pianificazione per Sistema telefonico (Cloud PBX) con connettività PSTN locale.
ms.openlocfilehash: 9715a04eaa4955ca1ccb4d9bef56b3502039c225
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58601261"
---
# <a name="plan-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>Pianificare Sistema telefonico con connettività PSTN locale in Skype for Business Server

> [!Important]
> Skype for Business Online verrà ritirato il 31 luglio 2021 dopo il quale il servizio non sarà più accessibile.  Inoltre, la connettività PSTN tra l'ambiente locale tramite Skype for Business Server o Cloud Connector Edition e Skype for Business Online non sarà più supportata.  Informazioni su come connettere la rete di telefonia locale a Teams tramite [Routing diretto.](/MicrosoftTeams/direct-routing-landing-page)

Informazioni sulle considerazioni sulla pianificazione per Sistema telefonico (Cloud PBX) con connettività PSTN locale.

Questo contenuto è rilevante se è già stato Skype for Business Server o Lync Server 2013 distribuito in locale. Per altri scenari, vedere [Soluzioni di telefonia Microsoft](/microsoftteams/cloud-voice-landing-page).

 Sistema telefonico connettività PSTN locale consente di sfruttare le funzionalità di Sistema telefonico (Cloud PBX) per gli utenti. Ciò può essere utile per gli scenari seguenti:

- Alcuni utenti di Skype for Business sono ospitati in locale e altri in Skype for Business Online. È ora possibile abilitare Sistema telefonico e funzionalità per gli utenti ospitati in Skype for Business Online, ma continuare a usare la connettività PSTN locale.

- Si dispone di una distribuzione locale e si desidera spostare alcuni o tutti gli utenti in Skype for Business Online, ma continuare a usare la connettività PSTN locale.

    > [!IMPORTANT]
    > Per abilitare correttamente gli utenti Sistema telefonico con connettività PSTN locale, il relativo indirizzo SIP deve essere nel proprio dominio. L'utilizzo del dominio predefinito per Microsoft 365 o Office 365, onmicrosoft.com, non è supportato. 

Per ulteriori informazioni sulle Sistema telefonico, incluse le licenze e i piani, vedere Piani per chiamate [PSTN per Skype for Business](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).

## <a name="feature-comparison"></a>Confronto delle funzionalità

Cloud PBX con connettività PSTN locale non offre lo stesso set di funzionalità di una soluzione VoIP aziendale locale. Per decidere se Cloud PBX con connettività PSTN locale fornirà il set di funzionalità giusto per l'organizzazione, vedere Ecco cosa si ottiene [con Cloud PBX.](/microsoftteams/here-s-what-you-get-with-phone-system?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2ftoc.json)

## <a name="benefits-and-planning-considerations"></a>Considerazioni sui vantaggi e sulla pianificazione

> [!CAUTION]
> I dispositivi Lync Telefono Edition DEVONO essere aggiornati al firmware minimo necessario nell'ambiente locale PRIMA di passare a Skype for Business Online.
Se si spostano gli utenti da locale a online prima di aggiornare il firmware, gli utenti non saranno in grado di connettersi utilizzando i telefoni. Per risolvere il problema, gli utenti devono essere spostati di nuovo nell'ambiente locale per aggiornare i telefoni al firmware minimo. NON TENTARE DI ESEGUIRE L'AGGIORNAMENTO AL FIRMWARE MINIMO O DI REIMPOSTARE IL TELEFONO PRIMA DI SPOSTARE DI NUOVO L'UTENTE NELL'AMBIENTE LOCALE.
Se viene eseguito un hard reset mentre il dispositivo non è il firmware minimo, per impostazione predefinita verrà utilizzato l'autenticazione PIN, che non è supportata in Skype for Business Online. Per ulteriori informazioni, vedere [Getting phones for Skype for Business Online.](https://support.office.com/article/Getting-phones-for-Skype-for-Business-Online-91f2d947-45fc-4fab-bd8b-2e313531c477?ui=en-US&amp;rs=en-US&amp;ad=US)

Distribuendo Sistema telefonico con connettività PSTN locale, è possibile spostare gli utenti nel cloud tramite Skype for Business Online al proprio ritmo, mantenendo la connettività PSTN locale. Se si dispone di un sistema PBX, continuare a utilizzarlo per fornire connettività PSTN per gli utenti che si spostano nel cloud. Una volta spostato un utente in Skype for Business Online e Sistema telefonico, il telefono PBX legacy non funzionerà più, ma il numero di telefono verrà instradato a uno qualsiasi dei client Skype for Business per PC o smart phone e telefoni da tavolo conformi Skype for Business. Dopo la portabilità, gli Sistema telefonico e gli utenti PBX legacy possono chiamarsi normalmente e effettuare/ricevere chiamate PSTN utilizzando il numero di telefono normale.

Potresti avere una funzionalità personalizzata o un componente aggiuntivo principale per il PBX legacy, ad esempio un call center. Se la funzionalità personalizzata non è attualmente disponibile in Sistema telefonico, è consigliabile lasciare gli utenti che richiedono tale funzionalità personalizzata in locale con il PBX legacy e convertire gli utenti che non devono accedere alla funzionalità personalizzata a Sistema telefonico con connettività PSTN locale.

Per un elenco dei sistemi PBX legacy che interoperabili direttamente con Skype for Business Server 2015, vedere [Infrastructure Qualified for Microsoft Lync.](../../../SfbPartnerCertification/lync-cert/qualified-ip-pbx-gateway.md) Se il sistema PBX non è in questo elenco, è possibile utilizzare un Session Border Controller per connettere il SISTEMA PBX con Sistema telefonico in Skype for Business Online.

### <a name="network-considerations-for-quality-and-performance"></a>Considerazioni sulla rete per qualità e prestazioni

Quando si distribuisce un servizio ospitato nel cloud come Sistema telefonico con connettività PSTN locale, è necessario tenere presente quanto segue. In una distribuzione di Skype for Business Server 2015 VoIP aziendale locale, tutta l'infrastruttura e i client si basano sulla rete aziendale. La qualità e le prestazioni di questa rete, fondamentale per audio e video di alta qualità, sono sotto il controllo diretto del personale aziendale. Con Sistema telefonico con connettività PSTN locale, sono coinvolte tre reti, due delle quali sono responsabili del cliente, ma solo una delle quali il personale aziendale ha il controllo diretto su:

- **Global Media Delivery Network di Microsoft** Infrastruttura e rete cloud globale di Microsoft. Sistema telefonico server e il traffico attraversano la rete.

- **Enterprise/Cloud PSTN Interconnect** Questa è la rete che connette l'azienda al cloud. Questo non è necessariamente lo stesso della connessione Internet generica.

- **Rete aziendale** La qualità dei supporti in tempo reale dipende in larga parte dalla propria rete, in particolare dalla rete WiFi e dalla qualità dell'interconnessione utilizzata per raggiungere il cloud.

> [!NOTE]
> Per ulteriori informazioni sull'ottimizzazione delle prestazioni in Skype for Business Online, vedere [Tune Skype for Business Online performance](https://support.office.com/article/Tune-Skype-for-Business-Online-performance-beec23c2-c5d6-4e84-a8af-e82aefca7802?ui=en-US&amp;rs=en-US&amp;ad=US). 

## <a name="prerequisites-for-using-phone-system-with-on-premises-pstn-connectivity"></a>Prerequisiti per l'Sistema telefonico con la connettività PSTN locale

Prima di poter configurare Sistema telefonico con connettività PSTN locale e spostare gli utenti in Skype for Business Online, è necessario verificare di disporre dei prerequisiti seguenti:

 **Versioni server locali.** Le versioni dei server nella distribuzione locale devono essere elencate nella tabella seguente per supportare Sistema telefonico con connettività PSTN locale.


| **Ruolo del server**                                       | **Versioni supportate\\**\*                                                                                         |
|:------------------------------------------------------|:-------------------------------------------------------------------------------------------------------------------|
| Federation Edge\*\*  <br/>                            | Skype for Business Server 2015  <br/>                                                                              |
| Server pool interno route federazione hop successivo  <br/> | Skype for Business Server 2015, marzo 2016 Aggiornamento cumulativo 6.0.9319.235 o versione successiva (Front End o Director)  <br/> |
| Front End User Server  <br/>                          | Skype for Business Server 2015  <br/> Lync Server 2013  <br/>                                                      |
| Edge Server  <br/>                                    | Skype for Business Server 2015  <br/>                                                                              |
| Mediation Server  <br/>                               | Skype for Business Server 2015  <br/> Lync Server 2013  <br/>                                                      |

\*Le versioni minime supportate sono:

- Skype for Business Server 2015, aggiornamento cumulativo di marzo 2016 6.0.9319.235

- Lync Server 2013 Aggiornamento cumulativo 5.0.8308.920 di luglio 2015

\*\*La route di federazione per tutti i domini SIP supportati deve essere instradato attraverso il server perimetrale Skype for Business Server 2015 che esegue l'aggiornamento cumulativo di marzo 2016 o versione successiva. Se il pool di utenti si trova in Lync Server 2013, il traffico del pool esterno rimane su Lync Server 2013 Edge Server. 

Inoltre, è necessario verificare quanto segue:

- **I VoIP aziendale locali sono configurati e testati per gli utenti locali** Sono inclusi i componenti di connettività PSTN. Per ulteriori informazioni, vedere gli argomenti seguenti se si utilizza Skype for Business Server 2015, vedere [Plan for VoIP aziendale in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) e Deploy VoIP aziendale in Skype for Business Server [2015](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md).

    Se si utilizza Lync Server 2013, vedere [Planning for VoIP aziendale in Lync Server 2013](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-enterprise-voice) e [Deploying VoIP aziendale in Lync Server 2013](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-enterprise-voice).

- **Sincronizzazione di Active Directory** È necessario configurare la sincronizzazione di Active Directory con Azure AD Connessione. Per ulteriori informazioni, vedere [Managing Azure AD Connessione](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect-whats-next/).

    > [!NOTE]
    > La versione di AAD Connessione utilizzata deve essere la versione 1.0.9125.0 o successiva. Se si utilizza una versione precedente degli strumenti Connessione AAD o DirSync, eseguire l'aggiornamento alla versione supportata. È possibile aggiornare l'installazione corrente e gestire tutte le regole personalizzate definite nell'ambiente. 

- **Configurare la distribuzione ibrida** Indipendentemente dal fatto che tutti gli utenti di Skype for Business siano attualmente ospitati online o locali o se si dispone di una combinazione di utenti, è necessario completare la procedura per configurare una distribuzione ibrida di Skype for Business Server o Lync Server 2013, come descritto in [Deploy hybrid connectivity between Skype for Business Server and Office 365](../../../SfbHybrid/hybrid/configure-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json). Per ulteriori informazioni di base sulle distribuzioni ibride, vedere [Plan hybrid connectivity between Skype for Business Server and Office 365](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json). 

    Se si utilizza Lync Server 2013, vedere [Lync Server 2013 ibrido.](/previous-versions/office/lync-server-2013/lync-server-2013-lync-server-2013-hybrid)

- **(Scelta consigliata) Active Directory Federation Services (AD FS).** È consigliabile distribuire ADFS per supportare Single Sign-on. Per ulteriori informazioni, vedere [Active Directory Federation Services (AD FS)](/previous-versions/windows/it-pro/windows-server-2003/cc736690(v=ws.10)).

Per informazioni sulla distribuzione di Sistema telefonico, vedere [Enable users for Sistema telefonico with on-premises PSTN connectivity in Skype for Business Server](enable-users-for-phone-system.md).