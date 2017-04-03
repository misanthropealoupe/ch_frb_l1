Broken pipeline?  The following sequence of commands will put all modules on their master branches,
update from git, and rebuild everything.

If you don't have all of these modules installed (e.g. you may not need simpulse, ch_frb_rfi, or ch_frb_l1,
depending on what you're doing), then you can probably just skip the uninstalled ones.
```
cd simd_helpers
git checkout master
git pull
make -j4 install
cd ..

cd sp_hdf5
git checkout master
git pull
make -j4 install
cd ..

cd simpulse
make clean uninstall
git checkout master
git pull
make -j4 install
cd ..

cd ch_frb_io
make clean uninstall
git checkout master
git pull
make -j4 install
cd ..

cd bonsai
make clean uninstall
git checkout master
git pull
make -j4 install
cd ..

cd rf_pipelines
make clean uninstall
git checkout master
git pull
make -j4 install
cd ..

cd ch_frb_rfi
make clean uninstall
git checkout master
git pull
make -j4 install
cd ..

cd ch_frb_l1
make clean
git checkout master
git pull
make -j4 all
cd ..
```