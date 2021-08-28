---
title: Configurare la rete per Skype Meeting Broadcast
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: micchan
ms.topic: article
ms.assetid: dfa736b9-4920-4f48-b8c0-b5487ec6086f
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- SMB
description: Informazioni sulla funzionalità Riunione Skype Broadcast di Skype for Business Online che consente di pianificare, produrre e trasmettere riunioni o eventi a un pubblico online di grandi dimensioni fino a 10.000 partecipanti.
ms.openlocfilehash: 998fbb0a0c077507731d8db09521d49e5c5d635f
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58594850"
---
# <a name="set-up-your-network-for-skype-meeting-broadcast"></a>Configurare la rete per Skype Meeting Broadcast

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Dopo aver [abilitato Riunione Skype broadcast Riunione Skype](enable-skype-meeting-broadcast.md) broadcast, è necessario configurare la rete. Eseguire questo passaggio se si vogliono tenere webinar e altre trasmissioni per utenti esterni all'azienda.

> [!IMPORTANT]
> Skype for Business Online è in ritiro il 31 luglio 2021, quando l'accesso al servizio terminerà. Incoraggiamo i clienti a iniziare l'aggiornamento a Microsoft Teams, il client principale per le comunicazioni e il lavoro in team in Microsoft 365.

Se non si ha esperienza nella configurazione del firewall, è consigliabile assumere un [partner Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) per eseguire questo passaggio.

Per ignorare questo passaggio e aggiungere un'altra azienda alla [federazione](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)in modo da poterle invitare a trasmettere, seguire i passaggi descritti in Consentire agli utenti di contattare utenti esterni Skype for Business utenti .

## <a name="step-1-set-up-allowed-domains"></a>Passaggio 1: Configurare i domini consentiti

Usare **uno** dei metodi seguenti per configurare i domini consentiti:

### <a name="method-1-use-the-admin-center"></a>Metodo 1: Usare l'interfaccia di amministrazione

1. Passare all'interfaccia di amministrazione e quindi nel riquadro di spostamento sinistro fare clic su **componenti** aggiuntivi Impostazioni Servizi e quindi scegliere  >  **&amp;** **Skype for Business**.

2. Nella pagina **Condivisione esterna** in **Eccezioni** dominio selezionare Tutti i domini sono bloccati tranne **e** immettere i domini seguenti, separati da una virgola (,):

   - noammeetings.lync.com

   - emeameetings.lync.com

   - apacmeetings.lync.com

   - resources.lync.com

3. Fare clic su **Salva**.

### <a name="method-2-use-windows-powershell"></a>Metodo 2: Usare Windows PowerShell

- Nel **menu Start fare clic con** il pulsante destro **del** mouse Windows PowerShell e scegliere Esegui **come amministratore.** Nella finestra **Windows PowerShell** digitare ogni riga e premere INVIO.

  ```PowerShell
  $r = New-CsEdgeDomainPattern -Domain "noammeetings.lync.com"
  ```

  ```PowerShell
  $s = New-CsEdgeDomainPattern -Domain "emeameetings.lync.com"
  ```

  ```PowerShell
  $t = New-CsEdgeDomainPattern -Domain "apacmeetings.lync.com"
  ```

  ```PowerShell
  $n = New-CsEdgeDomainPattern -Domain "resources.lync.com"
  ```

  ```PowerShell
  $newAllowList = New-CsEdgeAllowList -AllowedDomain $r,$s,$t,$n
  ```

  ```PowerShell
  Set-CsTenantFederationConfiguration -AllowedDomains $newAllowList
  ```

## <a name="step-2-add-skype-meeting-broadcast-domains-urls-and-ip-addresses"></a>Passaggio 2: Aggiungere Riunione Skype broadcast, URL e indirizzi IP

Il secondo passaggio del processo di configurazione consiste nell'aggiungere prima i domini necessari e quindi aggiungere gli indirizzi IP e gli URL necessari per il funzionamento di Riunione Skype Broadcast.

- **Aggiungere gli URL e gli indirizzi IP Skype for Business gli indirizzi IP dell'endpoint online** per vedere quali sono necessari [qui.](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo)

## <a name="set-up-skype-meeting-broadcast-in-hybrid-deployments-and-organizations"></a>Configurare Riunione Skype broadcast nelle distribuzioni ibride e nelle organizzazioni

Se si ha un'organizzazione di Skype for Business Online e una distribuzione locale di Lync Server 2010, Microsoft Lync Server 2013 e Skype for Business Server 2015 e si hanno utenti sia online che locali, è necessario eseguire altre operazioni di configurazione oltre a quelle precedenti per consentire all'organizzazione locale di comunicare con Skype for Business Online e consentire a tutti gli utenti di partecipare a una trasmissione Riunione Skype. Per sapere quali sono questi requisiti, vedere Configurare la distribuzione locale [per Riunione Skype Broadcast.](../../SfbServer/deploy/configure-skype-meeting-broadcast.md)

## <a name="related-topics"></a>Argomenti correlati

[Abilitare Skype Meeting Broadcast](enable-skype-meeting-broadcast.md)

[URL e intervalli di indirizzi IP per Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

[Configurare Skype for Business online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
