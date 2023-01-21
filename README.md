# GoSkel — My simple golang application skeleton

This is a simple Go application skeleton that should provide a quick start for new applications.

Create the directory within your go source environment where your new application will live. In this case, I will use `${USER}/go/src/github.com/nerdlem/mynewapp`. You might want to ckeckout this code at that new location, as follows:

```bash
git clone https://github.com/nerdlem/goskel.git "${GOPATH}/src/your/program"
```

After this step, the new directory should have been populated with the required files to setup and prepare your program according to these instructions.

> You might want to remove the `.git` directory so as to start without any history inherited from the skeleton.

## Prerequisites

This skeleton has been prepared based on a custom fork of the fantastic `github.com/spf13/cobra-cli`. You will also need to prepare the `go mod` environment as follows:

```bash
cd "${GOPATH}/src/your/program"
rm -rf .git
go install github.com/nerdlem/cobra-cli
go mod init
```

This branched `cobra-cli` version introduces the ability to pass templates via the configuration file. This allows for a more tailored generated application.

## Base customisation

Edit the enclosed `cobra.toml` file to taste. You will note that the file includes templates to generate the files that will be part of your application—you probably want to leave those parts alone.

Make sure you update the license, author and copyright related entries to taste.

## Viper for configuration file management

`github.com/spf13/viper` is another great library to use in your projects as it makes it easy to manage configuration files with environment variable overrides, tied to you command line flags. Personally, I tend to use Viper as much as I can, and therefore this is the command I would use to setup my application.

```bash
cobra-cli --config cobra.toml --viper init
```

After this step, you should have a functional application skeleton available.

## No Viper

If for some reason you don't need or want to use Viper, just omit the `--viper` option in the invocation above.

