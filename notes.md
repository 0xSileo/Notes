- What is formal verification ?

## For method supported

add submodule for exec api test :


git submodule add https://github.com/ethereum/execution-apis libs/execution-api

git config core.sparseCheckout true
echo "libs/execution-api/tests/*" >> .git/info/sparse-checkout
git submodule update --init --recursive
