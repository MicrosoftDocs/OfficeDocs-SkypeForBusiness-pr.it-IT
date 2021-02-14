---
title: Preparare l'ambiente
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b4e0ad1e-12e5-4130-aec1-d8c9cd3a5965
ms.collection:
- M365-collaboration
description: Informazioni su come preparare l'infrastruttura per la distribuzione di Sale di Microsoft Teams in modo da poter sfruttare tutte le funzionalità.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d0c5d5a1b0333a30b7730d6c8b91d06e67e291b4
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662431"
---
# <a name="prepare-your-environment"></a>Predisporre l'ambiente

Questa sezione contiene una panoramica dei passaggi necessari per preparare l'ambiente in modo da poter usare tutte le caratteristiche delle sale di Microsoft Teams.
  
1. Preparare un account del dispositivo per ogni console di Microsoft Teams Room. Per [informazioni dettagliate, vedere Distribuire](rooms-deploy.md) sale di Microsoft Teams.
    
2. Assicurarsi che sia disponibile una rete/connessione Internet funzionante per il dispositivo. 
    
   - Deve essere in grado di ricevere un indirizzo IP utilizzando la funzione PIÙ.TOT. Le sale di Microsoft Teams non possono essere configurate con un indirizzo IP statico all'avvio della prima unità, ma in seguito l'IP statico per il dispositivo potrebbe essere configurato sul dispositivo o sull'interruttore o router upstream.
   - Devono avere queste porte aperte (oltre ad aprire le porte normali per i supporti):
   - HTTPS: 443
   - HTTP: 80
   - Se la rete viene eseguita tramite un proxy, sono necessarie anche le informazioni sull'indirizzo del proxy o sullo script.
    
     > [!IMPORTANT]
     > La chat room di Microsoft Teams non supporta l'autenticazione proxy perché può interferire con il normale funzionamento della chat room. Assicurarsi che le sale di Microsoft Teams siano state esentate dall'autenticazione proxy prima di andare in produzione.
  
3. Per migliorare la tua esperienza, Microsoft raccoglie dati. Per consentire a Microsoft di raccogliere dati, consentire questi siti:

   - Endpoint client di telemetria: https://vortex.data.microsoft.com/
   - Endpoint delle impostazioni di telemetria: https://settings.data.microsoft.com/
    
### <a name="create-and-test-a-device-account"></a>Creare e testare un account del dispositivo

Un  *account dispositivo è*  un account utilizzato dal client Sale di Microsoft Teams per accedere alle funzionalità di Exchange, ad esempio il calendario, e per abilitare Skype for Business. Per [informazioni dettagliate, vedere Distribuire](rooms-deploy.md) sale di Microsoft Teams.
  
### <a name="check-network-availability"></a>Verificare la disponibilità della rete

Per funzionare correttamente, il dispositivo Sale di Microsoft Teams deve avere accesso a una rete cablata che soddisfi i requisiti seguenti:
  
- Accesso all'istanza di Active Directory o Azure Active Directory (Azure AD), nonché ai server Microsoft Exchange e Skype for Business.
- Accesso a un server in grado di fornire un indirizzo IP utilizzando LA funzione PIÙ.SEN. Le sale di Microsoft Teams non possono essere configurate con un indirizzo IP statico all'avvio della prima unità.
- Accesso alle porte HTTP 80 e 443.
- Porte TCP e UDP configurate [come](/skypeforbusiness/plan-your-deployment/network-requirements/ports-and-protocols) descritto in Requisiti di porta e protocollo per i server per l'implementazione locale di Skype for Business Server oppure URL e intervalli di indirizzi IP di Microsoft Teams e [Office 365](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US) per le implementazioni online di Microsoft Teams o Skype for Business.

> [!IMPORTANT]
> Assicurarsi di usare una connessione di rete cablata da 1 Gbps per garantire la larghezza di banda necessaria.

> [!NOTE]
> Gli aggiornamenti software per le sale di Microsoft Teams vengono scaricati automaticamente da Microsoft Store per le aziende. Vedi [i prerequisiti di Microsoft Store per le aziende](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business) e la formazione per verificare che la console della sala possa accedere al negozio e eseguire l'aggiornamento in autonomia.
  
### <a name="certificates"></a>Certificati

Il dispositivo Microsoft Teams Rooms usa certificati per Servizi Web Exchange, Microsoft Teams o Skype for Business, utilizzo della rete e autenticazione. Se i server correlati usano certificati pubblici, come per le distribuzioni online e per alcune distribuzioni locali, non è necessario eseguire altre azioni da parte dell'amministratore per installare i certificati. Se invece l'autorità di certificazione è un'Autorità di certificazione privata (tipica delle distribuzioni locali), il dispositivo deve considerare attendibile tale CA, ovvero avere i certificati a catena CA +CA installati nel dispositivo. L'aggiunta del dispositivo al dominio può eseguire automaticamente questa attività.
  
I certificati verranno installati come per qualsiasi altro client Windows. 
  
> [!NOTE]
> Per fare in modo che le sale di Microsoft Teams usino Skype for Business Server, potrebbero essere necessari certificati.
  
### <a name="proxy"></a>Proxy

La chat room di Microsoft Teams è progettata per ereditare le impostazioni del proxy dal sistema operativo Windows. Accedere al sistema operativo Windows nel modo seguente:
  
1. Nell'interfaccia utente di Microsoft Teams Rooms fare clic sull'icona a forma di ingranaggio Impostazioni, in cui verrà richiesta la password dell'amministratore locale nel dispositivo (la password predefinita è **sfb).**
2. Toccare  Impostazioni, quindi toccare il pulsante Vai a  **Windows,** passare al pulsante Accedi  amministratore e quindi fare clic sul pulsante Amministratore (se il computer fa parte di un dominio e scegliere Altro **utente,** quindi usare .\admin come nome utente).
3. Nella casella **di ricerca di Windows** digitare in regedit (premere a lungo lo schermo o fare clic con il pulsante destro del mouse e scegliere Esegui come **amministratore).**
4. Fare clic sulla HKEY_USERS cartelle radice (verrà visualizzato un elenco di SID utente del computer) verificare che la cartella radice HKEY_USERS selezionata.
       
5. Fare clic su File e quindi **scegliere Load Hive.**
6. Passare alla cartella **C:\Utenti\Skype** e digitare nella casella Nome file NTUSER.dat e premere il pulsante Apri

7. Ti verrà richiesto un nome di chiave per il nuovo hive caricato; digita Skype (ora dovresti vedere le impostazioni del Registro di sistema per l'Utente Skype).
 
8. Apri il codice Skype e cerca l'HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings quindi verifica che queste impostazioni siano immesse: 
    
    `[HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings]`
    
    `"MigrateProxy"=dword:00000001`
    
    `"ProxyEnable"=dword:00000001`
    
    `"ProxyServer"="xx.xx.xx.xx:8080"`
    
    Se ProxyServer non esiste, può essere necessario aggiungere questa chiave come stringa, modificare xx.xx.xx.xx:8080 nell'ip/host e nella porta del server proxy.
    
9. Dopo aver apportato le modifiche, evidenzia la chiave Utente Skype (cartella radice per Skype) e scegli scarica Hive dal menu file del Registro di sistema (ti verrà richiesta una conferma - seleziona **Sì).**
    
10. È ora possibile chiudere l'editor del Registro di sistema e digitare la logoff nella casella di ricerca di Windows.
    
11. Torna alla schermata di accesso, scegli **l'utente Skype.** Se tutti i passaggi precedenti sono stati completati correttamente, il dispositivo Microsoft Teams Rooms verrà eseguito correttamente.
    
Per usare questa applicazione, è necessario essere in grado di connettersi agli endpoint descritti di seguito. Per visualizzare gli indirizzi IP, espandere la sezione degli indirizzi IP sotto la tabella che descrive il flusso del traffico.
  
**Esempi di nome host/porta proxy firewall**

|Scopo|Origine o credenziali|Porta di origine|Destinazione|RETE CDN|ExpressRoute per Office 365|INDIRIZZO IP di destinazione|Porta di destinazione|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Autenticazione e identità  <br/> |Vedere [l'autenticazione e l'identità di Microsoft 365 e Office 365](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_Identity) <br/> |||
|Portale e condivisione  <br/> |Vedere [l'interfaccia di amministrazione di Microsoft 365 e la condivisione](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_Portal-identity) <br/> |||
|Segnalazione SIP  <br/> |Computer client o utente connesso  <br/> |Porte effimere  <br/> |\*contoso.com  <br/> |No  <br/> |Sì  <br/> |[Intervalli IP di Skype for Business](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443  <br/> |
|Conferenze Web di connessioni PSOM (Shared Object Model) persistenti  <br/> |Computer client o utente connesso  <br/> |Porte effimere  <br/> |\*contoso.com  <br/> |No  <br/> |Sì  <br/> |[Intervalli IP di Skype for Business](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443  <br/> |
|Download HTTPS  <br/> |Computer client o utente connesso  <br/> |Porte effimere  <br/> |\*contoso.com  <br/> |No  <br/> |Sì  <br/> |[Intervalli IP di Skype for Business](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443  <br/> |
|Audio  <br/> |Computer client o utente connesso  <br/> |TCP/UDP 50,000-50019  <br/> |\*contoso.com  <br/> |No  <br/> |Sì  <br/> |[Intervalli IP di Skype for Business](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443, UDP 3478, TCP/UDP 50,000-59,999  <br/> |
|Video  <br/> |Computer client o utente connesso  <br/> |TCP/UDP 50,020-50039  <br/> |\*contoso.com  <br/> |No  <br/> |Sì  <br/> |[Intervalli IP di Skype for Business](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443, UDP 3478, TCP/UDP 50,000-59,999  <br/> |
|Condivisione desktop  <br/> |Computer client o utente connesso  <br/> |TCP/UDP 50,040-50059  <br/> |\*contoso.com  <br/> |No  <br/> |Sì  <br/> |[Intervalli IP di Skype for Business](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443, 50.000-59.999  <br/> |
|Notifiche push di Lync Mobile per Lync Mobile 2010 nei dispositivi iOS. Non è necessario per i dispositivi mobili Android, Nokia Symbian o Windows Phone.  <br/> |Computer client o utente connesso  <br/> |Porte effimere  <br/> |\*contoso.com  <br/> |No  <br/> |Sì  <br/> |[Intervalli IP di Skype for Business](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 5223  <br/> |
|Telemetria di Skype  <br/> |Computer client o utente connesso  <br/> |Porte effimere  <br/> |skypemaprdsitus.trafficmanager.net  <br/> pipe.skype.com  <br/> |No  <br/> |No  <br/> |N/D  <br/> |TCP 443  <br/> |
|Suggerimenti rapidi per il client Skype  <br/> |Computer client o utente connesso  <br/> |Porte effimere  <br/> |quicktips.skypeforbusiness.com  <br/> |No  <br/> |No  <br/> |N/D  <br/> |TCP 443  <br/> |

> [!NOTE]
> Il carattere jolly contoso.com e broadcast.skype.com rappresenta un lungo elenco di nodi usati esclusivamente per Microsoft 365 o Office 365. 
  
### <a name="create-provisioning-packages"></a>Creare pacchetti di provisioning

Userai i pacchetti di provisioning per l'autenticazione Exchange Server, Microsoft 365 o Office 365.
  
### <a name="admin-group-management"></a>Gestione dei gruppi di amministratori

Dopo l'aggiunta al dominio, è possibile usare Criteri di gruppo o Gestione computer locale per impostare un gruppo di sicurezza come amministratore locale, come per un PC Windows nel dominio. Tutti i membri di questo gruppo di sicurezza possono immettere le proprie credenziali e sbloccare le impostazioni.
  
> [!NOTE]
> Se il dispositivo Sale di Microsoft Teams perde la fiducia con il dominio (ad esempio, se si rimuovono le sale di Microsoft Teams dal dominio dopo che è stato aggiunto al dominio), non sarà possibile eseguire l'autenticazione nel dispositivo e aprire le impostazioni. La soluzione alternativa consiste nell'accedere con l'account di amministratore locale. 
  
## <a name="local-accounts"></a>Account locali

### <a name="microsoft-teams-rooms-local-user-account"></a>Account utente locale di Microsoft Teams Rooms

L'account del dispositivo in genere non usa una password. È possibile assegnarle una password, ma ci sono conseguenze, tra cui la possibilità che gli utenti siano bloccati dall'applicazione console alla scadenza della password. Di conseguenza, l'amministratore deve assicurarsi che la password non scada.
  
### <a name="admin---local-administrator-account"></a>"Amministratore" - Account amministratore locale

La password predefinita di Microsoft Teams Rooms è impostata su "sfb". La password può essere cambiata localmente da Impostazioni di Windows a Windows o nel file AutoUnattend.xml (usare Gestione immagini di sistema Windows da ADK per apportare la modifica al \> file XML).
  
> [!CAUTION]
> Assicurarsi di cambiare la password di Microsoft Teams Rooms il più presto possibile. 
  
È anche possibile gestire la password di amministratore locale configurando un criterio di gruppo in cui gli amministratori di dominio sono amministratori locali.
  
La password di amministratore locale non viene inclusa come scelta durante l'installazione.
  
### <a name="machine-account"></a>Account computer

Come per qualsiasi dispositivo Windows, il nome del computer può essere rinominato facendo clic con il pulsante destro del mouse su Impostazioni \> su \> Rinomina PC.
  
 Se si vuole rinominare il computer dopo l'aggiunta a un dominio, usare il comando Rename-Computer PowerShell di Rename-Computer seguito dal nuovo nome del computer.
  
## <a name="related-topics"></a>Argomenti correlati

[Pianificare le sale di Microsoft Teams](rooms-plan.md)

[Requisiti per Microsoft Teams Rooms](requirements.md)
  
[Distribuire Microsoft Teams Rooms](rooms-deploy.md)
  
[Configurare una console per Microsoft Teams Rooms](console.md)
  
[Gestire Microsoft Teams Rooms](rooms-manage.md).

[Prerequisiti per Microsoft Store per le aziende e la formazione](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business) 
