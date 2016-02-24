<h1>Zadania do szkolenia</h1>
<a href="https://666786091374.signin.aws.amazon.com/console">Link do AWS</a>
<h2>Zadanie 1 - Pierwsza usługa - maszyna wirtualna</h2>
<ol>
	<li>Zaloguj się do AWS Console (użyj linku powyżej)</li>
	<li>Przełącz się na region Ireland lub Frankfurt (prawy górny róg)</li>
	<li>Z listy usług AWS wybierz EC2 (sekcja "Compute")</li>
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
	<li>Zaloguj się do swojej maszyny wirtualnej
		<ul>
			<li>Znajdź i zaznacz swoją maszynę wirtualną</li>
			<li>Kliknij szary przycisk „Connect” (nad listą instancji)</li>
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
			<li>Używaj maszyny wirtualnej w dowolnym celu</li>
		</ul>
	</li>
</ol>
<h2>ZADANIE 2 – SKALOWANIE W GÓRĘ</h2>
<ol>
	<li>Zaalokuj nowy adres publiczny (EIP)
		<ul>
			<li>Z listy usług AWS wybierz EC2 (lewy górny róg)</li>
			<li>Z panelu po lewej stronie wybierz "Elastic IPs" (zakładka "NETWORK & SECURITY")</li>
			<li>Kliknij niebieski przycisk "Allocate New Address"</li>
			<li>Potwierdź zamiar klikając niebieski przycisk "Yes, Allocate"</li>
			<li>Zamknij okno klikając niebieski przycisk "Close"</li>
		</ul>
	</li>
	<li>Podepnij EIP do istniejącej instancji
		<ul>
			<li>Zaznacz nowoutworzony EIP</li>
			<li>Kliknij szary przycisk "Actions" (nad listą) lub kliknij prawym przyciskiem myszy na EIP</li>
			<li>Wybierz opcję "Associate Address"</li>
			<li>Kliknij w textbox "Instance", znajdź i wybierz swoją instancję</li>
			<li>Kliknij niebieski przycisk "Associate"</li>
		</ul>
	</li>
	<li>Sprawdź wydajność swojej maszyny wirtualnej
		<ul>
			<li>Pobierz plik "benchmark.exe" z "\\morpheus\pub-Transfer\w\wryczko\FP_AWS_Training\benchmark.exe"
			<li>Zaloguj się do maszyny wirtualnej (opis w zadaniu 1)</li>
			<li>Skopiuj i odpal plik benchmark.exe z liczbą iteracji (domyślnie 10)</li>
			<li>Na maszynie m4.large test trwa niecałą minutę</li>
			<li>Zapisz czas wykonania programu</li>
		</ul>
	</li>
	<li>Utwórz obraz maszyny wirtualnej (AMI)
		<ul>
			<li>Przejdź do listy instancji</li>
			<li>Zaznacz swoją instancję</li>
			<li>Kliknij szary przycisk "Actions" (nad listą) lub kliknij prawym przyciskiem myszy na instancję</li>
			<li>Wybierz opcję "Image"->"Create Image"</li>
			<li>W polu "Instance name" wpisz dowolną nazwę obrazu</li>
			<li>Kliknij niebieski przycisk "Create Image"</li>
			<li>Zamknij okno klikając niebieski przycisk "Close"</li>
			<li>Przejdź do listy utworzonych obrazów klikając na panelu z lewej strony "AMIs" (zakładka "IMAGES")</li>
			<li>Poczekaj aż obraz będzie gotowy (3-4 min)</li>
		</ul>
	</li>
	<li>Utwórz maszynę wirtualną z obrazu AMI
		<ul>
			<li>
				<li>Przejdź do listy instancji</li>
				<li>Kliknij „Launch Instance”</li>
				<li>Step 1: Choose an Amazon Machine Image (AMI)
					<ul>
						<li>Wybierz z lewego panelu "My AMIs"</li>
						<li>Znajdź swój nowoutworzony obraz</li>
						<li>Kliknij niebieski przycisk "Select"</li>
					</ul>
				</li>
				<li>Step 2: Choose an Instance Type
					<ul>
						<li>Wybierz mocniejszą maszynę (np. m4.4xlarge)</li>
					</ul>
				</li>
				<li>Reszta kroków jak w zadaniu 1<li>
				<li>Tym razem nie musisz tworzyć nowego pliku-klucza. Możesz wybrać istniejący.</li>
			</li>
		</ul>
	</li>
	<li>Zacznij sprawdzać dostępność maszyny wirtualnej
		<ul>
			<li>Sprawdź adres IP (EIP)</li>
			<li>Na lokalnym komputerze odpal command line</li>
			<li>Użyj narzędzia ping: "ping {IP} -t"</li>
			<li>Nie zamykaj konsoli do końca zadania</li>
		</ul>
	</li>
	<li>Przełącz EIP (publiczny IP) między maszynami wirtualnymi
		<ul>
			<li>Przejdź do listy EIP</li>
			<li>Kliknij szary przycisk "Actions" (nad listą) lub kliknij prawym przyciskiem myszy na EIP</li>
			<li>Wybierz opcję "Associate Address"</li>
			<li>Kliknij w textbox "Instance", znajdź i wybierz swoją nową (mocniejszą) instancję</li>
			<li>Zaznacz opcje "Reassociation"</li>
			<li>Kliknij niebieski przycisk "Associate"</li>
		</ul>
	</li>
	<li>Zaobserwuj w command line, czy użytkownik odczuje "skalowanie"</li>
	<li>Sprawdź wydajność swojej nowej (mocniejszej) maszyny wirtualnej
		<ul>
			<li>Zaloguj się do maszyny przez RDP (jeżeli nie tworzyłeś nowego klucza, to hasło jest takie samo jak na starej maszynie)</li>
			<li>Zauważ, że plik "benchmark.exe" już się tam znajduje</li>
			<li>Odpal plik benchmark.exe z liczbą iteracji jak na pierwszej maszynie (domyślnie 10)</li>
			<li>Zapisz czas wykonania programu</li>
		</ul>
	</li>
	<li>Porównaj wyniki obu testów maszyn wirtualnych (słabszej i mocniejszej)</li>
</ol>