# kiss-icp-converter


Użyte repozytorium:

kiss-icp z GitHub: https://github.com/PRBonn/kiss-icp

laszip https://github.com/LASzip/LASzip.git


Instalacja kiss

pip install kiss-icp

Tworzenie Folderu

mkdir ros2_ws

Przejscie do ros2_ws

cd ros2_ws

klon z repo(z kropką na końcu)

git clone https://github.com/marcinmatecki/kiss-icp-converter.git .

Inicjuje submoduły w repozytorium.

git submodule init

Pobiera zawartość submodułów, w tym zagnieżdżone submoduły.

git submodule update --recursive

Kompilacja projektu

colcon build

STEP 1 bag->kiss

Nagrywanie danych z tematów 

ros2 bag record -o bag_kiss /kiss/frame /kiss/odometry

Uruchamia launch file, przekazując ścieżkę do pliku .bag i nazwę tematu.

ros2 launch kiss_icp odometry.launch.py bagfile:=(dir_bag) topic:=(topic_name)

STEP 2 bag -> session
Uruchomienie

ros2 run cpp_pubsub listener input_dir_bag output_dir

--------------------------

Instalation kiss

pip install kiss-icp

Creating a folder

mkdir ros2_ws

Changing to ros2_ws directory

cd ros2_ws

Cloning the repository (with a dot at the end)

git clone https://github.com/marcinmatecki/kiss-icp-converter.git .

Initializing submodules in the repository

git submodule init

Fetching the content of the submodules, including nested submodules

git submodule update --recursive

Building the project

colcon build

STEP 1: bag -> kiss

Recording data from topics

ros2 bag record -o bag_kiss /kiss/frame /kiss/odometry

Running the launch file, passing the path to the .bag file and topic name

ros2 launch kiss_icp odometry.launch.py bagfile:=(dir_bag) topic:=(topic_name)

STEP 2: bag -> session

Running

ros2 run cpp_pubsub listener input_dir_bag output_dir

