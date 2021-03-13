# fruits
A test project for [mmdjiji/cmake-learning](https://github.com/mmdjiji/cmake-learning).

## Deploy without install
```sh
cmake .
make
```

## Run
```sh
./fruits
```

## Deploy and install
```sh
cmake .
make && make install
```
After installation, you can use `fruits` command everywhere.

## Clean
```sh
make clean
```
Clean the object files.

## Uninstall
```sh
rm /usr/local/bin/fruits
```
