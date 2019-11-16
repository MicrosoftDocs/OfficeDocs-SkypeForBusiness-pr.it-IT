---
title: Preparare l'ambiente
ms.author: v-lanac
author: lanachin
ms.reviewer: sohailta
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.service: msteams
localization_priority: Normal
ms.assetid: b4e0ad1e-12e5-4130-aec1-d8c9cd3a5965
ms.collection:
- M365-collaboration
description: Questo articolo illustra i preparativi per l'infrastruttura per la distribuzione delle sale di Microsoft teams.
ms.openlocfilehash: b7bc3b7791edf88fd6882b67cdaa7d9b65e87741
ms.sourcegitcommit: 70bf1669442bbb50cb293c86d6a0c80fb3b2b55a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/16/2019
ms.locfileid: "38675804"
---
# <a name="prepare-your-environment"></a>Predisporre l'ambiente

Questa sezione contiene una panoramica dei passaggi necessari per preparare l'ambiente in modo da poter usare tutte le funzionalità di Microsoft teams rooms.
  
1. Preparare un account di dispositivo per ogni console Microsoft teams rooms. Per informazioni dettagliate, vedere [distribuire le sale di Microsoft teams](room-systems-v2.md) .
    
2. Verificare che sia disponibile una connessione Internet o una rete funzionante per il dispositivo. 
    
   - Deve essere in grado di ricevere un indirizzo IP tramite DHCP. (Le sale di Microsoft teams non possono essere configurate con un indirizzo IP statico al primo avvio dell'unità, ma in seguito è possibile configurare un IP statico per il dispositivo nel dispositivo o nell'interruttore o nel router upstream.)
   - Deve avere queste porte aperte (oltre ad aprire le normali porte per il contenuto multimediale):
   - HTTPS: 443
   - HTTP: 80
   - Se la rete viene eseguita tramite proxy, sarà necessario anche l'indirizzo proxy o le informazioni sullo script.
    
     > [!NOTE]
     > Microsoft teams Rooms non supporta l'input HDCP, che è stato osservato in modo da causare problemi con la funzionalità di ingesting HDMI (video, audio). Assicurarsi che le opzioni connesse alle sale di Microsoft teams siano disattivate.
  
3. Per migliorare l'esperienza acquisita, Microsoft raccoglie i dati. Per consentire a Microsoft di raccogliere dati, whitelist questi siti:

   - Endpoint client di telemetria:https://vortex.data.microsoft.com/
   - Endpoint delle impostazioni di telemetria:https://settings.data.microsoft.com/
    
### <a name="create-and-test-a-device-account"></a>Creare e testare un account di dispositivo

Un *account di dispositivo* è un account che il client di Microsoft teams Rooms USA per accedere alle caratteristiche di Exchange, come Calendar, e per abilitare Skype for business. Per informazioni dettagliate, vedere [distribuire le sale di Microsoft teams](room-systems-v2.md) .
  
### <a name="check-network-availability"></a>Verificare la disponibilità della rete

Per funzionare correttamente, il dispositivo Microsoft teams Rooms deve avere accesso a una rete cablata che soddisfa questi requisiti:
  
- Accedere all'istanza di Active Directory o di Azure Active Directory (Azure AD), nonché ai server di Microsoft Exchange e Skype for business.
- Accesso a un server in grado di specificare un indirizzo IP tramite DHCP. Le sale di Microsoft teams non possono essere configurate con un indirizzo IP statico.
- Accesso alle porte HTTP 80 e 443.
- Porte TCP e UDP configurate come descritto in [requisiti per la porta e il protocollo per i server](/skypeforbusiness/plan-your-deployment/network-requirements/ports-and-protocols) per le implementazioni locali di Skype for Business Server o per gli [URL e gli intervalli di indirizzi IP di Office 365](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US) per Microsoft teams o per le implementazioni di Skype for business online.

> [!IMPORTANT]
> Assicurati di usare una connessione di rete a 1 Gbps cablata per assicurarti che avrai la larghezza di banda necessaria.

> [!NOTE]
> Gli aggiornamenti software per le sale di Microsoft teams vengono scaricati automaticamente da Microsoft Store for business. Vedere [prerequisiti per Microsoft Store per le aziende e l'istruzione](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business) per verificare che la console della sala sia in grado di accedere allo Store e all'aggiornamento automatico.
  
### <a name="certificates"></a>Certificati

Il dispositivo Microsoft teams Rooms usa i certificati per i servizi Web Exchange, Microsoft teams o Skype for business, l'uso della rete e l'autenticazione. Se i server correlati usano certificati pubblici, che è il caso di una distribuzione online e di alcune distribuzioni locali, non devono essere necessarie ulteriori azioni da parte dell'amministratore per installare i certificati. Se invece l'autorità di certificazione è una CA privata (tipica per le distribuzioni locali), il dispositivo deve considerare attendibile la CA, che significa che nel dispositivo sono installati i certificati della catena CA + CA. L'aggiunta del dispositivo al dominio può eseguire questa attività automaticamente.
  
I certificati verranno installati nello stesso modo per qualsiasi altro client Windows. 
  
> [!NOTE]
> I certificati possono essere necessari per consentire a Microsoft teams Rooms di usare Skype for Business Server.
  
### <a name="proxy"></a>Proxy

Microsoft teams Rooms è progettato per ereditare le impostazioni proxy dal sistema operativo Windows. Accedere al sistema operativo Windows con il seguente modo:
  
1. Nell'interfaccia utente di Microsoft teams rooms, fare clic sull'icona dell'ingranaggio impostazioni in cui verrà richiesto di immettere la password di amministratore locale nel dispositivo (la password predefinita è **SFB**).
2. Toccare **Impostazioni** seguite toccando il pulsante **passa a Windows** e quindi toccando il pulsante Accedi all' **accesso per** l'amministratore e quindi facendo clic sul pulsante **amministratore** (se il computer è collegato al dominio, scegliere un **altro utente,** quindi usare .\Admin come nome utente).
3. Nella casella di **ricerca di Windows** in basso a sinistra digitare regedit (premere a lungo sullo schermo o fare clic con il pulsante destro del mouse e scegliere **Esegui come amministratore**).
4. Fare clic sulla cartella HKEY_USERS (verrà visualizzato un elenco di SID utente computer) verificare che sia selezionata l'opzione HKEY_USERS cartella radice.
       
5. Fare clic su file e quindi scegliere **Carica hive.**
6. Passare alla cartella **C:\Users\Skype** e digitare nella casella nome file Ntuser. dat e premere il pulsante Apri

7. Verrà richiesto il nome di una chiave per l'hive appena caricato; digita Skype (ora dovresti vedere le impostazioni del registro di sistema per l'utente Skype).
 
8. Aprire il tasto Skype e passare a HKEY_USERS impostazioni di \Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet, quindi verificare che le impostazioni siano immesse: 
    
    `[HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings]`
    
    `"MigrateProxy"=dword:00000001`
    
    `"ProxyEnable"=dword:00000001`
    
    `"ProxyServer"="xx.xx.xx.xx:8080"`
    
    Se ProxyServer non esiste può essere necessario aggiungere questa chiave come stringa, cambiare XX. XX. XX. XX: 8080 con l'indirizzo IP/host e la porta del server proxy.
    
9. Dopo aver apportato le modifiche, evidenziare il codice utente Skype (cartella radice per Skype) e scegliere Scarica hive dal menu file del registro di sistema (verrà richiesto di confermare-selezionare **Sì** ).
    
10. Ora è possibile chiudere l'editor del registro di sistema e digitare disconnessione nella casella di ricerca di Windows.
    
11. Di nuovo nella schermata di accesso, scegliere l'utente **Skype** . Se tutti i passaggi precedenti hanno avuto esito positivo, il dispositivo Microsoft teams Rooms verrà eseguito l'accesso.
    
Per usare questa applicazione, è necessario essere in grado di connettersi agli endpoint descritti di seguito. Per visualizzare gli indirizzi IP, espandere la sezione indirizzo IP sotto la tabella che descrive il flusso di traffico.
  
**Esempi di nome host proxy firewall/porta**

|Scopo|Origine o credenziali|Porta di origine|Destinazione|CDN|ExpressRoute per Office 365|IP di destinazione|Porta di destinazione|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Autenticazione e identità  <br/> |Vedere [autenticazione e identità di Office 365](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_Identity) <br/> |||
|Portale e condivisione  <br/> |Vedere [portale e condivisione di Office 365](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_Portal-identity) <br/> |||
|Segnalazione SIP  <br/> |Computer client o utente connesso  <br/> |Porte effimere  <br/> |\*. contoso.com  <br/> |No  <br/> |Sì  <br/> |[Intervalli di indirizzi IP Skype for business](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443  <br/> |
|Conferenze Web con connessioni PSOM (Persistent Shared Object Model)  <br/> |Computer client o utente connesso  <br/> |Porte effimere  <br/> |\*. contoso.com  <br/> |No  <br/> |Sì  <br/> |[Intervalli di indirizzi IP Skype for business](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443  <br/> |
|Download HTTPS  <br/> |Computer client o utente connesso  <br/> |Porte effimere  <br/> |\*. contoso.com  <br/> |No  <br/> |Sì  <br/> |[Intervalli di indirizzi IP Skype for business](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443  <br/> |
|Audio  <br/> |Computer client o utente connesso  <br/> |TCP/UDP 50000-50019  <br/> |\*. contoso.com  <br/> |No  <br/> |Sì  <br/> |[Intervalli di indirizzi IP Skype for business](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443, UDP 3478, TCP/UDP 50000-59.999  <br/> |
|Video  <br/> |Computer client o utente connesso  <br/> |TCP/UDP 50020-50039  <br/> |\*. contoso.com  <br/> |No  <br/> |Sì  <br/> |[Intervalli di indirizzi IP Skype for business](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443, UDP 3478, TCP/UDP 50000-59.999  <br/> |
|Condivisione desktop  <br/> |Computer client o utente connesso  <br/> |TCP/UDP 50040-50059  <br/> |\*. contoso.com  <br/> |No  <br/> |Sì  <br/> |[Intervalli di indirizzi IP Skype for business](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443, 50000-59.999  <br/> |
|Notifiche push di Lync mobile per Lync Mobile 2010 nei dispositivi iOS. Questa operazione non è necessaria per i dispositivi mobili Android, Nokia Symbian o Windows Phone.  <br/> |Computer client o utente connesso  <br/> |Porte effimere  <br/> |\*. contoso.com  <br/> |No  <br/> |Sì  <br/> |[Intervalli di indirizzi IP Skype for business](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 5223  <br/> |
|Telemetria Skype  <br/> |Computer client o utente connesso  <br/> |Porte effimere  <br/> |skypemaprdsitus.trafficmanager.net  <br/> pipe.skype.com  <br/> |No  <br/> |No  <br/> |N/D  <br/> |TCP 443  <br/> |
|Client Skype suggerimenti rapidi  <br/> |Computer client o utente connesso  <br/> |Porte effimere  <br/> |quicktips.skypeforbusiness.com  <br/> |No  <br/> |No  <br/> |N/D  <br/> |TCP 443  <br/> |

> [!NOTE]
> Il carattere jolly per contoso.com e broadcast.skype.com rappresenta un lungo elenco di nodi usati esclusivamente per Office 365. 
  
### <a name="create-provisioning-packages"></a>Creare pacchetti di provisioning

Si utilizzeranno i pacchetti di provisioning per eseguire l'autenticazione in Exchange Server o Office 365.
  
### <a name="admin-group-management"></a>Gestione dei gruppi di amministratori

Dopo l'aggiunta di un dominio, è possibile usare criteri di gruppo o Gestione computer locale per impostare un gruppo di sicurezza come amministratore locale come per un PC Windows nel proprio dominio. Tutti gli utenti membri di tale gruppo di sicurezza possono immettere le proprie credenziali e sbloccare le impostazioni.
  
> [!NOTE]
> Se il dispositivo Microsoft teams Rooms perde fiducia nel dominio (ad esempio, se si rimuovono le sale di Microsoft teams dal dominio dopo l'aggiunta di un dominio), non sarà possibile eseguire l'autenticazione nel dispositivo e aprire le impostazioni. La soluzione alternativa consiste nell'eseguire l'accesso con l'account di amministratore locale. 
  
## <a name="local-accounts"></a>Account locali

### <a name="microsoft-teams-rooms-local-user-account"></a>Account utente locale di Microsoft teams rooms

L'account del dispositivo in genere non usa una password. È possibile assegnarle una password, ma esistono conseguenze, inclusa la possibilità che gli utenti vengano bloccati dall'applicazione console quando la password scade. Di conseguenza, l'amministratore deve fare in modo che la password non sia consentita per la scadenza.
  
### <a name="admin---local-administrator-account"></a>"Amministratore"-account di amministratore locale

La password predefinita di Microsoft teams Rooms è impostata su "SFB". La password può essere modificata localmente passando alle impostazioni \> di Windows o al file Autounattend. XML (usare Windows System Image Manager da ADK per apportare la modifica al file XML).
  
> [!CAUTION]
> Assicurarsi di cambiare la password di Microsoft teams Rooms il più presto possibile. 
  
È anche possibile gestire la password di amministratore locale impostando un criterio di gruppo in cui gli amministratori di dominio vengono resi amministratori locali.
  
La password di amministratore locale non è inclusa come scelta durante l'installazione.
  
### <a name="machine-account"></a>Account del computer

Analogamente a qualsiasi dispositivo Windows, il nome del computer può essere rinominato facendo clic con il \> pulsante \> destro del mouse nelle impostazioni relative a Rinomina PC.
  
 Se si vuole rinominare il computer dopo averla aggiunta a un dominio, usare il comando Rinomina-computer di PowerShell seguito dal nuovo nome del computer.
  
## <a name="see-also"></a>Vedere anche

[Pianificare le sale di Microsoft Teams](skype-room-systems-v2-0.md)

[Requisiti di Microsoft teams rooms](requirements.md)
  
[Distribuire le sale di Microsoft Teams](room-systems-v2.md)
  
[Configurare una console Microsoft teams rooms](console.md)
  
[Gestire le sale di Microsoft Teams](skype-room-systems-v2.md)

[Prerequisiti per Microsoft Store per le aziende e l'istruzione](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business) 
