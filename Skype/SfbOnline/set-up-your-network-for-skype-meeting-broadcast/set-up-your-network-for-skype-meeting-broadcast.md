---
title: La configurazione della rete per la trasmissione riunione Skype
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: micchan
ms.date: 01/22/2018
ms.topic: article
ms.assetid: dfa736b9-4920-4f48-b8c0-b5487ec6086f
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- SMB
description: Informazioni sulla funzionalità di trasmissione riunione Skype di Skype Business online che consente inoltre di pianificazione, prodotti e trasmissione riunioni o eventi ai gruppi di destinatari in linea di grandi dimensioni fino a 10.000 partecipanti.
ms.openlocfilehash: 62c1f1fea7042230210d123c6d7fb88ff839d6f4
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/03/2018
---
# <a name="set-up-your-network-for-skype-meeting-broadcast"></a>La configurazione della rete per la trasmissione riunione Skype

Dopo aver [Abilitare trasmissione riunione Skype](enable-skype-meeting-broadcast.md) trasmissione riunione Skype, è necessario configurare la rete. Eseguire questo passaggio se si desidera mantenere webinar e altre trasmissioni per gli utenti all'esterno dell'azienda.
  
Se non hai dimestichezza con la configurazione del firewall, può essere utile assumere un [partner Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) che se ne occupi al posto tuo.
  
Per ignorare questo passaggio e aggiungere invece business diversa per la federazione in modo che possono essere invitati alle trasmissioni, seguire i passaggi descritti in [Consenti agli utenti di contatti esterni Skype per gli utenti aziendali](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).
  
## <a name="step-1-set-up-allowed-domains"></a>Passaggio 1: Impostare i domini consentiti

Per impostare i domini consentiti, utilizzare **uno** dei metodi seguenti:
  
### 

 **Metodo 1: Utilizzare l'interfaccia di amministrazione di Office 365**
  
1. Visitare il **Centro di amministrazione di Office 365** e quindi la barra di spostamento sinistra fare clic su **Impostazioni** > **servizi &amp; componenti aggiuntivi**e quindi fare clic su **Skype per le aziende**.
    
2. Nella pagina **condivisione esterna** in **eccezioni di dominio**, selezionare **tutti i domini vengono bloccati, ad eccezione**e immettere i seguenti domini separati da una virgola (,):
    
  - noammeetings.Lync.com
    
  - emeameetings.Lync.com
    
  - apacmeetings.Lync.com
    
  - Resources.Lync.com
    
3. Fai clic su **Salva**.
    
### 

 **Metodo 2: Utilizzare Windows PowerShell**
  
- Dal **Menu Start di** **Windows PowerShell** pulsante destro del mouse e fare clic su **Esegui come amministratore**. Nella finestra di **Windows PowerShell** , digitare ogni riga e premere INVIO.
    
  ```
  $r = New-CsEdgeDomainPattern -Domain "noammeetings.lync.com"
  ```

  ```
  $s = New-CsEdgeDomainPattern -Domain "emeameetings.lync.com"
  ```

  ```
  $t = New-CsEdgeDomainPattern -Domain "apacmeetings.lync.com"
  ```

  ```
  $n = New-CsEdgeDomainPattern -Domain "resources.lync.com"
  ```

  ```
  $newAllowList = New-CsEdgeAllowList -AllowedDomain $r,$s,$t,$n
  ```

  ```
  Set-CsTenantFederationConfiguration -AllowedDomains $newAllowList
  ```

## <a name="step-2-add-skype-meeting-broadcast-domains-urls-and-ip-addresses"></a>Passaggio 2: Aggiungere Skype riunione trasmissione domini, gli URL e IP indirizzi

Il secondo passaggio del processo di installazione è consente di aggiungere i domini necessarie e quindi aggiungono gli indirizzi IP e gli URL che sono necessari per trasmettere riunione Skype per l'utilizzo.
  
- **Aggiungere Skype necessarie per gli URL degli endpoint Business Online e gli indirizzi IP verificando quali sono necessari** [di seguito](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo).
    
## <a name="set-up-skype-meeting-broadcast-in-hybrid-deployments-and-organizations"></a>Configurazione di trasmissione riunione Skype nelle organizzazioni e le distribuzioni ibride

Se sono Skype per le organizzazioni aziendali in linea e una distribuzione locale di Lync Server 2010, Microsoft Lync Server 2013 e Skype per Business Server 2015 e avere agli utenti sia online e locale, sono disponibili altre operazioni di installazione è necessario eseguire Oltre a quelli sopra per abilitare l'organizzazione locale comunicare con Skype Business online e consentire a tutti gli utenti siano in grado di creare e partecipare a una riunione Skype trasmissione. Per verificare quali sono i requisiti, vedere [configurare la distribuzione in locale per la trasmissione riunione Skype](https://go.microsoft.com/fwlink/?LinkId=617070).
  
## <a name="related-topics"></a>See also

[Abilitare Skype Meeting Broadcast](enable-skype-meeting-broadcast.md)
  
[URL e intervalli di indirizzi IP per Office 365](http://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  
[Configurare Skype for Business online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
  
 
