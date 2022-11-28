# This container will install Bio-Tradis from master
#
FROM debian:bullseye-slim

#  Install the dependancies
RUN apt-get update -qq && apt-get install -y sudo make wget unzip zlib1g-dev cpanminus gcc bzip2 libncurses5-dev libncursesw5-dev libssl-dev r-base git libxml-libxml-perl libgd-gd2-perl bioperl bwa smalt tabix samtools locales

#  Set locales (required for running in Singularity)
RUN   sed -i -e 's/# \(en_GB\.UTF-8 .*\)/\1/' /etc/locale.gen && \
      touch /usr/share/locale/locale.alias && \
      locale-gen
ENV   LANG     en_GB.UTF-8
ENV   LANGUAGE en_GB:en
ENV   LC_ALL   en_GB.UTF-8

RUN cpanm IPC::System::Simple DateTime::Locale DateTime Dist::Zilla Moose Text::CSV ExtUtils::MakeMaker Getopt::Long Try::Tiny Exception::Class
RUN cpanm Dist::Zilla::Plugin::AutoPrereqs Dist::Zilla::Plugin::Encoding Dist::Zilla::Plugin::FileFinder::ByName Dist::Zilla::Plugin::MetaResources Dist::Zilla::Plugin::PkgVersion Dist::Zilla::Plugin::PodWeaver Dist::Zilla::Plugin::RequiresExternal Dist::Zilla::Plugin::RunExtraTests Dist::Zilla::PluginBundle::Git Dist::Zilla::PluginBundle::Starter
RUN cpanm --force XML::DOM::XPath
RUN cpanm --force Bio::Seq Bio::SeqIO