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
localization_priority: Normal
f1keywords: None
ms.custom:
- SMB
description: Informazioni sulla funzionalità Skype meeting broadcast di Skype for business online che consente di pianificare, produrre e trasmettere riunioni o eventi a un ampio pubblico online fino a 10.000 partecipanti.
ms.openlocfilehash: 95ad00be416a53e6e861ce4e9f235bded8e8075a
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40990981"
---
# <a name="set-up-your-network-for-skype-meeting-broadcast"></a>Configurare la rete per Skype Meeting Broadcast

Dopo aver [abilitato Skype meeting broadcast](enable-skype-meeting-broadcast.md) Skype meeting broadcast, è necessario configurare la rete. Eseguire questa procedura se si vogliono tenere webinar e altre trasmissioni per gli utenti esterni all'azienda.

Se non si ha esperienza con la configurazione del firewall, prendere in considerazione l'assunzione di un [partner Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) per eseguire questo passaggio.

Per ignorare questo passaggio e aggiungere un altro business alla Federazione in modo da poterlo invitare alle trasmissioni, seguire i passaggi descritti in [consentire agli utenti di contattare utenti Skype for business esterni](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).

## <a name="step-1-set-up-allowed-domains"></a>Passaggio 1: configurare i domini consentiti

Usare **uno** dei metodi seguenti per configurare i domini consentiti:

## #

 **Metodo 1: usare l'interfaccia di amministrazione**

1. Accedere all'interfaccia di amministrazione e quindi fare clic su**componenti aggiuntivi servizi &amp; ** **Impostazioni** > nella barra di spostamento sinistra e quindi scegliere **Skype for business**.

2. Nella pagina **condivisione esterna** in **eccezioni di dominio**Selezionare **tutti i domini sono bloccati eccetto**e immettere i domini seguenti, separati da una virgola (,):

   - noammeetings.lync.com

   - emeameetings.lync.com

   - apacmeetings.lync.com

   - resources.lync.com

3. Fai clic su **Salva**.

## #

 **Metodo 2: usare Windows PowerShell**

- Nel **menu Start**fare clic con il pulsante destro del mouse su **Windows PowerShell** e scegliere **Esegui come amministratore**. Nella finestra di **Windows PowerShell** Digitare ogni riga e premere INVIO.

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

## <a name="step-2-add-skype-meeting-broadcast-domains-urls-and-ip-addresses"></a>Passaggio 2: aggiungere domini, URL e indirizzi IP di Skype meeting broadcast

Il secondo passaggio del processo di configurazione è la prima volta che si aggiungono i domini necessari e quindi si aggiungono gli indirizzi IP e gli URL necessari per il funzionamento di Skype meeting broadcast.

- **Aggiungere gli URL e gli indirizzi IP dell'endpoint Skype for business online necessari per vedere quali sono necessari** [qui](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo).

## <a name="set-up-skype-meeting-broadcast-in-hybrid-deployments-and-organizations"></a>Configurare Skype meeting broadcast in distribuzioni e organizzazioni ibride

Se si ha un'organizzazione di Skype for business online e una distribuzione locale di Lync Server 2010, Microsoft Lync Server 2013 e Skype for Business Server 2015 e gli utenti sono online e locali, è necessario eseguire altre operazioni di configurazione oltre a quelli descritti sopra, per consentire all'organizzazione locale di comunicare con Skype for business online e consentire a tutti gli utenti di partecipare a una riunione Skype meeting broadcast. Per vedere quali sono questi requisiti, vedere [configurare la distribuzione locale per Skype meeting broadcast](https://go.microsoft.com/fwlink/?LinkId=617070).

## <a name="related-topics"></a>Argomenti correlati

[Abilitare Skype Meeting Broadcast](enable-skype-meeting-broadcast.md)

[URL e intervalli di indirizzi IP per Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

[Configurare Skype for Business online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)



