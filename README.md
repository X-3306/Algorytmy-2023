# Algorytmy-2023
Proste algorytmy.

Welcome to the Algorytmy-2023 wiki!

# Algorytmy-2023

# Algorytm sortowania bąbelkowego:
Ten algorytm polega na porównywaniu dwóch sąsiadujących elementów i zamianie ich kolejności, jeśli są one w złym porządku. Powtarzamy ten proces aż do momentu, gdy cała lista zostanie posortowana.

# Algorytm sortowania przez wstawianie:
W tym algorytmie każdy element jest porównywany z elementami po jego lewej stronie, aż znajdzie swój odpowiednią pozycję. Elementy po jego prawej stronie są przesuwane w prawo, aby zrobić miejsce dla elementu w odpowiedniej pozycji.

# Algorytm sortowania szybkiego:
Ten algorytm polega na wybieraniu elementu nazywanego "pivotem" i porównywaniu pozostałych elementów z tym pivotem. Elementy mniejsze od pivota są umieszczane po lewej stronie, a większe po prawej. Następnie proces jest powtarzany dla obu podzbiorów aż do momentu, gdy cała lista zostanie posortowana.

# Prosty skrypt w języku Python wykorzystujący algorytm sortowania bąbelkowego:

`def bubble_sort(arr):`
    `n = len(arr)`
    `for i in range(n):`
        `for j in range(0, n-i-1):`
            `if arr[j] > arr[j+1] :`
                `arr[j], arr[j+1] = arr[j+1], arr[j]`
    `return arr`




# Algorytm wyszukiwania liniowego:
Ten algorytm polega na przeszukiwaniu listy w poszukiwaniu określonej wartości. Wszystkie elementy są porównywane z wartością, aż zostanie znaleziona szukana wartość.

# Algorytm wyszukiwania binarnego:
Ten algorytm działa tylko na posortowanych listach. Polega na porównywaniu środkowego elementu z szukaną wartością. Jeśli wartość jest mniejsza niż środkowy element, to przeszukiwane jest tylko lewe poddrzewo. W przeciwnym razie przeszukiwane jest tylko prawe poddrzewo.

# Prosty skrypt w języku Python wykorzystujący algorytm wyszukiwania binarnego:

`def binary_search(arr, low, high, x):`
    `if high >= low:`
        `mid = (high + low) // 2`
        `if arr[mid] == x:`
            `return mid`
        `elif arr[mid] > x:`
            `return binary_search(arr, low, mid - 1, x)`
        `else:`
            `return binary_search(arr, mid + 1, high, x)`
    `else:`
        `return None`



# Algorytm DFS:
Ten algorytm polega na przeszukiwaniu grafu w głąb. Zaczynamy od wybranego wierzchołka i przechodzimy przez jego sąsiadów, a następnie rekurencyjnie przechodzimy przez sąsiadów kolejnych wierzchołków, aż odwiedzimy wszystkie wierzchołki.

# Algorytm BFS:
Ten algorytm polega na przeszukiwaniu grafu poziomami. Zaczynamy od wybranego wierzchołka i przechodzimy przez wszystkich jego sąsiadów. Następnie przechodzimy do sąsiadów sąsiadów, aż odwiedzimy wszystkie wierzchołki.

# Algorytm Dijkstry:
Ten algorytm służy do znajdowania najkrótszej ścieżki w grafie z jednym źródłem. Zaczynamy od wybranego źródła i przypisujemy mu odległość zero. Następnie przypisujemy pozostałym wierzchołkom nieskończoną wartość i relaksujemy krawędzie, aby znaleźć najkrótszą ścieżkę do każdego wierzchołka.

# Prosty skrypt w języku Python wykorzystujący algorytm DFS:

`def DFS(graph, start):`
    `visited = set()`
    `stack = [start]`
    `while stack:`
        `vertex = stack.pop()`
        `if vertex not in visited:`
            `visited.add(vertex)`
            `stack.extend(graph[vertex] - visited)`
    `return visited`



# Algorytm Jarvisa:
Ten algorytm służy do znajdowania otoczki wypukłej dla zbioru punktów. Zaczynamy od najniższego punktu i przechodzimy do kolejnych, wybierając zawsze punkt, który znajduje się najbardziej z lewej strony. Proces powtarzamy, aż wrócimy do punktu początkowego.

# Algorytm Grahama:
Ten algorytm również służy do znajdowania otoczki wypukłej dla zbioru punktów. Zaczynamy od najniższego punktu i sortujemy pozostałe punkty według kąta, który tworzą z osią OX. Następnie przeprowadzamy proces łączenia punktów, tworząc w ten sposób otoczkę wypukłą.

## Prosty skrypt w języku Python wykorzystujący algorytm Jarvisa:

`def jarvis(points):`
    `n = len(points)`
    `hull = []`
    `l = np.argmin(points, axis=0)`
    `hull.append(points[l])`
    `p = l`
    `while True:`
        `q = (p + 1) % n`
        `for i in range(n):`
            `if np.cross(points[i] - points[p], points[q] - points[p]) < 0:`
                `q = i`
        `if q == l:`
            `break`
        `hull.append(points[q])`
        `p = q`
    `return hull`




