---
title: Distribuire il bypass multimediale in Cloud Connector Edition
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0ebba3a4-6124-434c-84aa-32b1cc3345bc
description: Leggere questo argomento per informazioni sulla procedura per distribuire il bypass multimediale con Cloud Connector Edition versione 2.0 e successive.
ms.openlocfilehash: 6ce46df02295810367556e735897cd9ce912b4c7e8aa15f6db5ffb66d38d4574
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54289434"
---
# <a name="deploy-media-bypass-in-cloud-connector-edition"></a>Distribuire il bypass multimediale in Cloud Connector Edition
 
> [!Important]
> Cloud Connector Edition andrà in pensione il 31 luglio 2021 insieme a Skype for Business Online. Dopo l'aggiornamento dell'organizzazione a Teams, informazioni su come connettere la rete di telefonia locale a Teams tramite [Routing diretto](/MicrosoftTeams/direct-routing-landing-page).

Leggere questo argomento per informazioni sulla procedura per distribuire il bypass multimediale con Cloud Connector Edition versione 2.0 e successive. 
  
Il bypass multimediale consente a un client di inviare contenuti multimediali direttamente all'hop successivo PSTN (Public Switched Telephone Network), un gateway o session border controller (SBC), ed eliminare il componente Cloud Connector Edition dal percorso multimediale. Vedi anche [Pianificare il bypass multimediale in Cloud Connector Edition.](plan-for-media-bypass-in-cloud-connector-edition.md)
  
## <a name="enable-media-bypass"></a>Abilita bypass multimediale

Per abilitare il bypass multimediale, è necessario configurare il nome DNS del servizio Web di bypass multimediale e attivare il bypass multimediale nella configurazione tenant. Il servizio Web bypass multimediale viene distribuito automaticamente in ogni Mediation Server. Un amministratore tenant deve selezionare un nome per un servizio vocale ibrido (sito) e questo nome deve derivare da un dominio SIP registrato per la voce ibrida. Il nome del servizio deve essere lo stesso in tutti i dispositivi Cloud Connector e in tutti i siti PSTN indipendentemente dalla posizione del client. Il servizio Web deve essere disponibile solo internamente nella rete.
  
Un amministratore tenant deve configurare un record A DNS in Active Directory di produzione interna. Se si dispone di un ambiente multis sito complesso, vedere l'esempio in Esempio: record DNS del sito Web bypass multimediale [in ambienti multis](deploy-media-bypass-in-cloud-connector.md#Example)sito complessi. Il record DNS deve essere risolto solo per i client di rete interni. non deve essere risolto per i client di rete esterni.
  
Dopo aver configurato DNS, connettersi a Skype for Business Online utilizzando Remote PowerShell con Skype for Business credenziali di amministratore. Per ulteriori informazioni, vedere [Set up your computer for Windows PowerShell.](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  
Nella sessione di PowerShell immettere i comandi seguenti per abilitare il bypass multimediale:
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
$mediabypass = New-CsNetworkMediaBypassConfiguration -AlwaysBypass $true -Enabled $true
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

L'abilitazione del bypass multimediale è un processo in due passaggi. Il cmdlet New-CsNetworkMedia non salva immediatamente la nuova configurazione. crea solo le impostazioni in memoria. L'oggetto creato da questo cmdlet deve essere salvato in una variabile e quindi assegnato alla proprietà MediaBypassSettings della configurazione di rete. Per ulteriori informazioni, vedere [Example: media bypass web site DNS records in complex multi-site environments](deploy-media-bypass-in-cloud-connector.md#Example).
  
La replica tra i componenti locali e online può richiedere fino a 24 ore, pertanto Microsoft consiglia di eseguire i comandi necessari prima di abilitare gli utenti.
  
## <a name="confirm-media-bypass-settings"></a>Verificare le impostazioni di bypass multimediale

Puoi controllare le impostazioni di bypass multimediale come indicato di seguito. 
  
Per controllare la replica online nel pool tenant, eseguire il comando seguente in PowerShell remoto:
  
```powershell
Get-CsTenantHybridConfiguration -LocalStore
Get-CsNetworkConfiguration -LocalStore
```

Per controllare la replica locale, connettersi ai Mediation Server cloud Connector, eseguire il comando seguente in PowerShell e verificare che Enabled=True e AlwaysBypass=True
  
```powershell
Get-CsNetworkConfiguration -LocalStore
```

Per controllare le impostazioni del client, disconnettersi dal client Skype for Business, accedere di nuovo e verificare che il client abbia ricevuto l'URL del servizio come segue:
  
1. Aprire %appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog. 
    
2. Cercare hybridconfigserviceinternalurl e verificare che l'URL corrisponda a quello definito.
    
## <a name="change-media-bypass-parameters"></a>Modificare i parametri di bypass multimediale

Gli amministratori tenant possono modificare il nome DNS del servizio Web eseguendo il cmdlet seguente:
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
```

> [!IMPORTANT]
> I client devono disconnettersi e accedere per ottenere il nuovo nome del servizio e riconoscere la modifica. 
  
## <a name="temporarily-disable-media-bypass"></a>Disabilitare temporaneamente il bypass multimediale

Questo scenario può essere utile per la risoluzione dei problemi o la manutenzione. Per disabilitare il servizio, eseguire i cmdlet seguenti:
  
```powershell
$mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

Dopo aver apportato la modifica, potrebbe essere necessario del tempo per la replica delle modifiche in tutti i connettori cloud. Per controllare lo stato della replica, eseguire il cmdlet seguente in PowerShell sui Mediation Server cloud Connector: 
  
```powershell
Get- CsNetworkConfiguration -LocalStore
```

Dopo la replica delle modifiche, il servizio Web nel Mediation Server inizierà a rifiutare le richieste client per il servizio di bypass multimediale.
  
## <a name="disable-media-bypass-permanently"></a>Disabilitare il bypass multimediale in modo permanente

Per disabilitare definitivamente il bypass multimediale, un amministratore tenant deve eseguire i comandi seguenti: 
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl  $null
    $mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false 
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass 
```

Un amministratore dovrà anche rimuovere gli indirizzi Web per il bypass multimediale dai server DNS interni. Dopo aver apportato la modifica, potrebbe essere necessario del tempo per la replica delle modifiche in tutte le appliance del connettore cloud. 
  
## <a name="example-media-bypass-web-site-dns-records-in-complex-multi-site-environments"></a>Esempio: record DNS del sito Web bypass multimediale in ambienti multis sito complessi
<a name="Example"> </a>

I client riceveranno l'indirizzo Web del servizio Web bypass multimediale da un server DNS interno. Il nome del servizio Web sarà lo stesso in tutti i dispositivi Cloud Connector e nei siti PSTN del connettore cloud. In un ambiente multisito complesso, è consigliabile utilizzare i criteri DNS di Windows 2016 per la gestione del traffico basato su Geo-Location, in modo che i client possano essere reindirizzati al servizio Web locale per la propria rete. 
  
Per ulteriori informazioni sui criteri DNS Windows 2016, vedere [Use DNS Policy for Geo-Location Based Traffic Management with Primary Servers](/windows-server/networking/dns/deploy/primary-geo-location).
  
Di seguito è riportato un esempio di configurazione per una società con diversi siti Windows 2016 DNS Policy for Geo-Location Based Traffic Management.
  
Il nome del servizio di bypass è "hybridvoice.adatum.biz".
  
Il sito di Amsterdam dispone di quattro appliance Cloud Connector distribuite con i seguenti indirizzi IP di Mediation Server:
  
- 192.168.1.45
    
- 192.168.1.46
    
- 192.168.1.47
    
- 192.168.1.48
    
Il sito di Seattle dispone di tre appliance Cloud Connector distribuite con i seguenti indirizzi IP di Mediation Server:
  
- 10.10.1.8
    
- 10.10.1.9
    
- 10.10.1.10
    
Utilizzando Geo-Location gestione del traffico in base al traffico, i server DNS verrebbero configurati come segue:
  
1. Creare subnet client DNS per entrambe le subnet di Amsterdam e Seattle.
    
2. Creare ambiti di zona DNS per adatum.biz per Amsterdam e Seattle.
    
3. Creare record DNS in ogni ambito di zona DNS.
    
    Amsterdam
    
   - Digitare A;
    
   - Name : hybridvoice nella adatum.biz DNS
    
   - Destinazione: 192.168.1.45
    
     Creare record aggiuntivi per ulteriori mediation server
    
   - 192.168.1.46
    
   - 192.168.1.47
    
   - 192.168.1.48
    
     Seattle
    
   - Tipo A
    
   - Name : hybridvoice in adatum.biz DNS zone
    
   - Destinazione: 10.10.1.8
    
     Creare record aggiuntivi per ulteriori mediation server
    
   - 10.10.1.9
    
   - 10.10.1.10
    
4. Creare il criterio DNS che connette le subnet client agli ambiti di zona appropriati per garantire la risoluzione DNS desiderata.
    
A questo punto, i client che estituiscono query DNS dalla subnet di Amsterdam per hybridvoice.adatum.biz restituiranno il valore 192.168.1.45, 192.168.1.46, 192.168.1.47 e 192.168.1.48, mentre i client che estituiscono lo stesso modulo di query Seattle restituiranno 10.10.1.8, 10.10.1.9 e 10.10.1.10.

> [!NOTE]
> Se l'appliance CCE non sembra ottenere le impostazioni aggiornate, verificare se l'appliance è in grado di contattare il tenant tramite PowerShell remoto. È possibile utilizzare Remote PowerShell per controllare lo stato dell'appliance con Get-CsHybridPSTNAppliance oppure usare PowerShell nell'host CCE per controllare lo stato con Get-CcApplianceStatus.

  
## <a name="see-also"></a>Vedere anche
<a name="Example"> </a>

[Pianificare il bypass multimediale in Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md)