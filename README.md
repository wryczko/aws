<h1>Zadania do szkolenia</h1>
<a href="https://666786091374.signin.aws.amazon.com/console">Link do AWS</a>
<h2>Zadanie 1 - Pierwsza usługa - maszyna wirtualna</h2>
<ol>
	<li>Zaloguj się do AWS Console (użyj linku powyżej)</li>
	<li>Przełącz się na region Ireland lub Frankfurt (prawy górny róg)</li>
	<li>Z listy usług wybierz EC2 (lewy górny róg)</li>
	<li>Wybierz „Instances” lub "Running instances", a następnie „Launch Instance”</li>
	<li>Dobierz konfigurację
		<ul>
			<li>Step 1: Choose an Amazon Machine Image (AMI): "Windows Server 2012 R2 Base" (piąta od góry)
				<ul>
					<li>Znajdź "Windows Server 2012 R2 Base" (piąty obraz od góry)</li>
					<li>Kliknij niebieski przycisk "Select"</li>
				</ul>
			</li>
			<li>Step 2: Choose an Instance Type: coś z dwoma rdzeniami i min 3GB ramu (np. m4.large, c4.large)
				<ul>
					<li>Znajdź i zaznacz typ/moc instancji "m4.large" (szósta od góry)</li>
					<li>Kliknij szary przycisk "Next: Configure Instance Details"</li>
				</ul>
			</li>
			<li>Step 3: Configure Instance Details: wszystko domyślnie
				<ul>
					<li>Zostaw wszystko domyślnie</li>
					<li>Kliknij szary przycisk "Next: Add Storage"</li>
				</ul>
			</li>
			<li>Step 4: Add Storage
				<ul>
					<li>Podaj rozmiar domyślnej partycji (min 30GB)</li>
					<li>Kliknij szary przycisk "Next: Tag Instance"</li>
				</ul>
			</li>
			<li>Step 5: Tag Instance: w polu "value" podaj nazwę swojej maszyny
				<ul>
					<li>W polu "value" podaj nazwę swojej maszyny (będzie potrzebna do indentyfikacji na liście)</li>
					<li>Kliknij szary przycisk "Next: Configure Security Group"</li>
				</ul>
			</li>
			<li>Step 6: Configure Security Group
				<ul>
					<li>Wybierz "Select an existing security group"</li>
					<li>Wybierz Security Group "default"</li>
					<li>Sprawdź czy ma ona otwarty port 3389</li>
					<li>Kliknij niebieski przycisk "Review and Launch"</li>
				</ul>
			</li>
			<li>Step 7: Review Instance Launch
				<ul>
					<li>Sprawdź wprowadzoną konfigurację</li>
					<li>Kliknij niebieski przycisk "Launch" (prawy dolny róg)</li>
				</ul>
			</li>
		</ul>
	</li>
	<li>Select an existing key pair or create a new pair
		<ul>
			<li>Wybierz "Create a new key pair"</li>
			<li>Dowolnie nazwij klucz</li>
			<li>Kliknij szary przycisk "Download Key Pair"</li>
		</ul>
	</li>
	<li>Kliknij niebieski przycisk "Launch Instances"</li>
	<li>Przejdź do listy instancji np. klikając w niebieski przycisk "View Instances"</li>
	<li>Znajdź swoją maszynę wirtualną i kliknij szary przycisk „Connect” (nad listą instancji)</li>
	<li>Connect To Your Instance
		<ul>
			<li>Pobierz plik RDP klikając w szary przycisk "Download Remote Desktop File"</li>
			<li>Pobierz hasło
				<ul>
					<li>Kliknij w szary przycisk "Get Password"</li>
					<li>Poczekaj aż odblokuje się możliwość pobrania hasła (2-3 min)</li>
					<li>Kliknij w przycisk "Choose file"</li>
					<li>Znajdź i wybierz uprzednio pobrany plik/klucz</li>
					<li>Kliknij w szary przycisk "Decrypt Password"</li>
					<li>Skopiuj hasło</li>
					<li>Zamknij okno klikając w niebieski przycisk "Close"</li>
				</ul>
			</li>
			<li>Użyj pobranego pliku RDP i hasła do zalogowania się na maszynę wirtualną</li>
		</ul>
	</li>
</ol>
<h2>ZADANIE 2 – SKALOWANIE W GÓRĘ</h2>
<ol>
	<li>Zaalokuj nowy adres publiczny (EIP)</li>
	<li>Podepnij EIP do istniejącej instancji i sprawdź jej dostępność</li>
	<li>Zmień zawartość dysku (np. utworzyć plik na pulpicie)</li>
	<li>Utwórz obraz istniejącej maszyny wirtualnej (AMI)</li>
	<li>Skonfiguruj nową większą instację EC2 korzystając z nowopowstałego obrazu</li>
	<li>Zaloguj się do maszyny przez RDP (hasło z oryginału)</li>
</ol>