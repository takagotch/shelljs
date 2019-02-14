### shelljs
---
https://github.com/shelljs/shelljs


```
shx mkdir -p foo
shx touch foo/bar.txt
shx rm -rf foo

npm install -g shelljs

rm -rf foo.txt bar.txt
exec echo hello
```

```js
var shell = require('shelljs');
if (!shell.which('git')) {
  shell.echo('Sorry, this script requires git');
  shell.exit(1);
}
shell.rm('-rf', 'out/Release');
shell.cp('-r', 'stuff/', 'out/Release');
shell.cd('lib');
shell.ls('*.js').forEach(function (file) {
  shell.sed('-i', 'BUILD_VERSION', 'v0.1.2', file);
  shell.sed('-i', /^.*REPLACE_THIS_LINW.*$/, '', file);
  shell.sed('', /.*REPLACE_LINE_WITH_MACRO.*\n/, shell.cat('macro.js'), file);
});
shell.cd('..');
if (shell.exec('git commit -am "Auto-commit"').code !== 0) {
  shell.echo('Error: Git commit failed');
  shell.exit(1);
}


shell.grep('--', 'v', 'path/to/file');
shell.cp('-R', '-dir', 'outdir');

var shell = require('shelljs');
shell.echo('hello world');

var str = cat('file*.txt');
var str = cat('file1', 'file2');
var str = cat(['file1', 'file2']);

chmod(755, '/Users/brandon');
chmod('755', '/Users/brandon');
chmod('u+x', '/Users/brandon');
chmod('-R', 'a-w', '/Users/brandon');

cp('file1', 'dir1');
cp('-R', 'path/to/dir/', '~/newCopy/');
cp('-Rf', '/tmp/*', '/usr/local/*', '/home/tmp');
cp('-Rf', ['/tmp/*', '/usr/local/*'], '/home/tmp');

pushd('/etc');
pushd('+1');

echo(process.cwd());
pushd('/etc');
echo(process.cwd());
popd();
echo(process.cwd());

echo('hello world');
var str = echo('hello world');
echo('-n', 'no newline at end');

var version = exec('node --version', {silent:true}).stdout;
var child = exec('some_long_running_process', {async:true});
child.stdout.on('data', function(data){
});

exec('some_long_running_process', function(code, stdout, stderr){
  console.log('Exit code:', code);
  console.log('Program output:', stdout);
  console.log('Program stderr:', stderr);
});

find('src', 'lib');
find(['src', 'lib']);
find('.').filter(function(file) { return file.match(/\.js$/); });

grep('-v', 'GLOBAL_VARIABLE', '*.js');
grep('GLOBAL_VARIABLE', '*.js');

var str = head({'-n': 1}, 'file*.txt');
var str = head('file1', 'file2');
var str = head(['file1', 'file2']);

ln('file', 'newlink');
ln('-sf', 'file', 'existing');

ls('projs/*.js');
ls('-R', '/users/me', '/tmp');
ls('-R', ['/users/me', '/tmp']);
ls('-l', 'file.txt');

mkdir('-p', '/tmpa/b/c/d', '/tmp/e/f/g');
mkdir('-p', ['/tmp/a/b/c/d', '/tmp/e/f/g']);

mv('-n', 'file', 'dir/');
mv('file1', 'file2', 'dir/');
mv(['file1', 'file2'], 'dir/');

rm('-rf', '/tmp/*');
rm('some_file.txt', 'another_file.txt');
rm(['some_file.txt', 'another_file.txt']);

sed('-i', 'PROGRAM_VERSION', 'v0.1.3', 'source.js');
sed(/.*DELETE_THIS_LINE.*\n/, '', 'source.js');
sed(/(\w+)\s(\w+)/, '$2, $1', 'file.txt');

set('-e');
set('+e');

sort('foo.txt', 'bar.txt');
sort('-r', 'foo.txt');

var str = tail({'-n': 1}, 'file*.txt');
var str = tail('file1', 'file2');
var str = tail(['file1', 'file2']);

var tmp = tempdir();

if (test('-d', path));
if (!test('-f', path)) continue;

cat('input.txt').to('output.txt');

cat('input.txt').toEnd('output.txt');

touch('source.js');
touch('-c', 'path/to/file.js');
touch({ '-r': 'referenceFile.txt' }, 'path/to/file.js');
touch({ date: new Date('December 17,1995 03:24:00') }, 'path/to/file.js');

uniq('foo.txt');
uniq('-i', 'foo.txt');
uniq('-cd', 'foo.txt', 'bar.txt');

var nodeExec = which('node');

var foo = ShellString('hello world');

grep('foo', 'file1.txt', 'file2.txt').sed(/o/g, 'a').to('output.txt');
echo('files with o\'s in the name:\n' + ls().grep('o'));
cat('test.js').exec('node');

var sh = require('shelljs');
var silentState = sh.config.silent;
sh.config.silent = true;
sh.config.silent = silentState;

require('shelljs/global');
config.fatal = true;
cp('this_file_does_not_exist', '/dev/null');

config.verbose = true;
cd('dir/');
rm('-rf', 'foo.txt', 'bar.txt');
exec('echo hello');

config.globOptions = {nodir: true};

var shell = require('shelljs');
shell.config.reset();
```

```json
{
  fatal: false,
  globOptions: {},
  maxdepth: 255,
  noglob: false,
  silent: false,
  verbose: false,
}
```
