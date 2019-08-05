---
title: Pianificare il sistema telefonico in Office 365 con connettività PSTN locale in Skype for Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/26/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 021a4c0b-d5de-4155-a506-650d758624aa
description: Informazioni sulle considerazioni sulla pianificazione per il sistema telefonico in Office 365 (cloud PBX) con connettività PSTN locale.
ms.openlocfilehash: 1ca12d1680b56612c2e6f3a1785ee615138294ce
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/25/2019
ms.locfileid: "36195890"
---
# <a name="plan-phone-system-in-office-365-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>Pianificare il sistema telefonico in Office 365 con connettività PSTN locale in Skype for Business Server

Informazioni sulle considerazioni sulla pianificazione per il sistema telefonico in Office 365 (cloud PBX) con connettività PSTN locale.

Questo contenuto è pertinente se si dispone già di Skype for Business Server o Lync Server 2013 distribuito in locale. Per altri scenari, vedere [soluzioni](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/msft-telephony-solutions)per la telefonia Microsoft.

 Il sistema telefonico in Office 365 con connettività PSTN locale consente di sfruttare le funzionalità del sistema telefonico (cloud PBX) per gli utenti. Ciò può essere utile per gli scenari seguenti:

- I tuoi utenti di Skype for business sono ospitati in locale e in altre persone ospitati in Skype for business online. Ora è possibile abilitare il sistema telefonico nelle funzionalità e funzionalità di Office 365 per gli utenti ospitati in Skype for business online, ma continuare a usare la connettività PSTN locale.

- Si dispone di una distribuzione locale e si vuole trasferire alcuni o tutti gli utenti a Skype for business online, ma continuare a usare la connettività PSTN locale.

    > [!IMPORTANT]
    > Per abilitare correttamente gli utenti per il sistema telefonico in Office 365 con connettività PSTN locale, l'indirizzo SIP deve essere nel proprio dominio. L'uso del dominio predefinito per Office 365, onmicrosoft.com, non è supportato. 

Per altre informazioni sul sistema telefonico in Office 365, incluse le licenze e i piani, vedere [piani per chiamate PSTN per Skype for business](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).

## <a name="feature-comparison"></a>Confronto delle caratteristiche

Cloud PBX con connettività PSTN locale non offre lo stesso set di caratteristiche di una soluzione VoIP aziendale completamente locale. Per decidere se Cloud PBX con connettività PSTN locale fornirà il set di funzionalità appropriato per l'organizzazione, vedere [Ecco cosa si ottiene con Cloud PBX](https://go.microsoft.com/fwlink/?LinkId=715517).

## <a name="benefits-and-planning-considerations"></a>Considerazioni sui vantaggi e la pianificazione

> [!CAUTION]
> I dispositivi Lync Phone Edition devono essere aggiornati al firmware minimo richiesto nell'ambiente locale prima di passare a Skype for business online.
Se gli utenti vengono spostati da locale a online prima di aggiornare il firmware, gli utenti non potranno connettersi con i loro telefoni. Per risolvere il problema, gli utenti devono essere spostati di nuovo nell'ambiente locale per aggiornare i telefoni al firmware minimo. NON PROVARE A ESEGUIRE L'AGGIORNAMENTO AL FIRMWARE MINIMO O A REIMPOSTARE IL TELEFONO PRIMA DI RIPORTARE L'UTENTE NELL'AMBIENTE LOCALE.
Se viene eseguita una reimpostazione hardware mentre il dispositivo non è al minimo firmware, l'impostazione predefinita sarà l'uso dell'autenticazione PIN, che non è supportata in Skype for business online. Per altre informazioni, vedere [come ottenere telefoni per Skype for business online](https://support.office.com/en-us/article/Getting-phones-for-Skype-for-Business-Online-91f2d947-45fc-4fab-bd8b-2e313531c477?ui=en-US&amp;rs=en-US&amp;ad=US).

Distribuendo il sistema telefonico in Office 365 con connettività PSTN locale, è possibile trasferire gli utenti nel cloud tramite Skype for business online con il proprio ritmo, mantenendo la connettività PSTN locale. Se si ha un PBX, è possibile continuare a usarlo per ottenere la connettività PSTN per gli utenti spostati nel cloud. Dopo che un utente è stato spostato in Skype for business online e nel sistema telefonico in Office 365, il loro telefono PBX legacy non funzionerà più, ma il loro numero di telefono verrà indirizzato a qualsiasi client Skype for business per PC o smartphone, nonché telefono da tavolo compatibile con Skype for business s. Una volta convertito, il sistema telefonico in Office 365 gli utenti e gli utenti PBX legacy possono chiamarsi normalmente e effettuare/ricevere chiamate PSTN usando il loro normale numero di telefono.

Potrebbe essere disponibile una caratteristica personalizzata o un componente aggiuntivo importante per il PBX legacy, ad esempio un Call Center. Se la caratteristica personalizzata non è attualmente disponibile nel sistema telefonico in Office 365, è consigliabile abbandonare gli utenti che richiedono la funzionalità personalizzata locale con il PBX legacy e semplicemente trasferire gli utenti che non hanno bisogno di accedere alla funzionalità personalizzata al sistema telefonico in Office 365 con la connettività PSTN locale.

Per un elenco di PBX legacy che interagiscono direttamente con Skype for Business Server 2015, vedere l' [infrastruttura qualificata per Microsoft Lync](https://docs.microsoft.com/SkypeForBusiness/lync-cert/qualified-ip-pbx-gateway). Se il PBX non è presente nell'elenco, è possibile usare un controller di bordo della sessione per connettere il PBX con il sistema telefonico in Office 365 in Skype for business online.

### <a name="network-considerations-for-quality-and-performance"></a>Considerazioni sulla rete per qualità e prestazioni

Quando si distribuisce un servizio ospitato da cloud, come il sistema telefonico in Office 365 con connettività PSTN locale, è necessario tener presente quanto segue. In una distribuzione VoIP aziendale di Skype for Business Server 2015, tutta l'infrastruttura e i client si trovano nella rete aziendale. La qualità e le prestazioni di questa rete, che è fondamentale per l'audio e il video di alta qualità, sono sotto il diretto controllo dello staff aziendale. Con il sistema telefonico in Office 365 con connettività PSTN locale, sono presenti tre reti, due delle quali il cliente è responsabile, ma solo uno dei quali il personale dell'organizzazione ha il controllo diretto:

- **Rete di distribuzione multimediale globale Microsoft** Rete e infrastruttura cloud globale Microsoft. Office 365 e sistema telefonico in Office 365 server e traffico attraversano questa rete.

- **Interconnessione PSTN Enterprise/Cloud** Questa è la rete che connette l'azienda al cloud di Office 365. Questo non è necessariamente lo stesso della connessione Internet generica.

- **Rete propria dell'organizzazione** La qualità dei contenuti multimediali in tempo reale dipende fortemente dalla propria rete: in particolare la rete WiFi e la qualità dell'interconnessione usata per raggiungere il cloud di Office 365.

> [!NOTE]
> Per altre informazioni sull'ottimizzazione delle prestazioni in Skype for business online, Vedi [ottimizzare le prestazioni di Skype for business online](https://support.office.com/en-us/article/Tune-Skype-for-Business-Online-performance-beec23c2-c5d6-4e84-a8af-e82aefca7802?ui=en-US&amp;rs=en-US&amp;ad=US). 

## <a name="prerequisites-for-using-phone-system-in-office-365-with-on-premises-pstn-connectivity"></a>Prerequisiti per l'uso del sistema telefonico in Office 365 con connettività PSTN locale

Prima di configurare il sistema telefonico in Office 365 con connettività PSTN locale e di trasferire gli utenti in Skype for business online, è necessario verificare che siano disponibili i prerequisiti seguenti:

 **Versioni server locali.** Le versioni dei server nella distribuzione locale devono essere elencate nella tabella seguente per supportare il sistema telefonico in Office 365 con connettività PSTN locale.


| **Ruolo del server**                                       | **Versioni supportate\\**\*                                                                                         |
|:------------------------------------------------------|:-------------------------------------------------------------------------------------------------------------------|
| Bordo federativo\*\*  <br/>                            | Skype for Business Server 2015  <br/>                                                                              |
| Routing federativo del server interno del pool successivo  <br/> | Skype for Business Server 2015, marzo 2016 aggiornamento cumulativo 6.0.9319.235 o versione successiva (front-end o Director)  <br/> |
| Server utenti front-end  <br/>                          | Skype for Business Server 2015  <br/> Lync Server 2013  <br/>                                                      |
| Edge Server  <br/>                                    | Skype for Business Server 2015  <br/>                                                                              |
| Mediation Server  <br/>                               | Skype for Business Server 2015  <br/> Lync Server 2013  <br/>                                                      |

\*Le versioni minime supportate sono:

- Skype for Business Server 2015, marzo 2016 aggiornamento cumulativo 6.0.9319.235

- Lync Server 2013 luglio 2015 aggiornamento cumulativo 5.0.8308.920

\*\*La route federativo per tutti i domini SIP supportati deve essere instradata tramite il server Edge di Skype for Business Server 2015 che usa l'aggiornamento cumulativo di marzo 2016 o superiore. Se il pool di utenti si trova in Lync Server 2013, il traffico del pool esterno rimane in Lync Server 2013 Edge Server. 

È inoltre necessario verificare quanto segue:

- La **voce aziendale locale è configurata e testata per gli utenti locali** Sono inclusi i componenti di connettività PSTN. Per altre informazioni, vedere gli argomenti seguenti se si usa Skype for Business Server 2015, vedere [pianificare VoIP aziendale in Skype for Business server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) e [distribuire VoIP aziendale in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md).

    Se si usa Lync Server 2013, vedere [pianificazione di VoIP aziendale in Lync server 2013](https://technet.microsoft.com/library/gg413081%28v=ocs.15%29.aspx) e [distribuzione di VoIP aziendale in Lync Server 2013](https://technet.microsoft.com/EN-US/library/gg412876%28v=ocs.15%29.aspx).

- **Sincronizzazione di Active Directory** È necessario configurare la sincronizzazione di Active Directory con Azure AD Connect. Per altre informazioni, vedere [gestione di Azure ad Connect](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect-whats-next/).

    > [!NOTE]
    > La versione di AAD Connect usata deve essere la versione 1.0.9125.0 o successiva. Se si usa una versione precedente degli strumenti AAD Connect o DirSync, eseguire l'aggiornamento alla versione supportata. È possibile aggiornare l'installazione corrente e gestire le regole personalizzate definite nell'ambiente. 

- **Configurare la distribuzione ibrida** Se tutti gli utenti di Skype for business sono attualmente ospitati online o in locale oppure se si ha una combinazione, è necessario completare la procedura per configurare una distribuzione ibrida di Skype for Business Server o Lync Server 2013, come descritto in [deploy Hybrid connettività tra Skype for Business Server e Office 365](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md). Per altre informazioni di base sulle distribuzioni ibride, vedere [pianificare la connettività ibrida tra Skype for Business Server e Office 365](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json). 

    Se si usa Lync Server 2013, vedere [Lync server 2013 Hybrid](https://technet.microsoft.com/EN-US/library/jj204805%28v=ocs.15%29.aspx).

- **Consigliato Active Directory Federation Services (ADFS).** È consigliabile distribuire ADFS per supportare single sign-on. Per altre informazioni, vedere [Active Directory Federation Services (ADFS)](https://technet.microsoft.com/en-us/library/cc736690%28v=ws.10%29.aspx).

Per informazioni sulla distribuzione di sistemi telefonici in Office 365, vedere [abilitare gli utenti per il sistema telefonico in office 365 con connettività PSTN locale in Skype for Business Server](enable-users-for-phone-system.md).


